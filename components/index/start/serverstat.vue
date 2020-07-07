<template>
  <b-card class="gl-bg-white-30 rounded shadow">
    <template v-slot:header>
      <MCSubtitle class="text-center">
        Server Status
      </MCSubtitle>
    </template>
    <stat
      v-for="(stat, key) in stats"
      :key="`serverstat-${stat.name}`"
      :name="key"
      :max-players="stat.max_players"
      :current-players="stat.current_players"
      :version="stat.version"
      :status="stat.status"
    />
  </b-card>
</template>

<script>
/* eslint-disable camelcase */
import MCSubtitle from '~/components/mc/mc-subtitle'
import Stat from '~/components/index/start/serverstat/stat'

export default {
  components: {
    MCSubtitle,
    Stat
  },
  data () {
    return {
      stats: {
        Survival: {
          name: 'survival',
          version: '',
          current_players: 0,
          max_players: 0,
          status: 2
        },
        Civil: {
          name: 'civil',
          version: '',
          current_players: 0,
          max_players: 0,
          status: 2
        },
        Creative: {
          name: 'creative',
          version: '',
          current_players: 0,
          max_players: 0,
          status: 2
        },
        Lobby: {
          name: 'lobby',
          version: '',
          current_players: 0,
          max_players: 0,
          status: 2
        }
      }
    }
  },
  created () {
    for (const stat in this.stats) {
      this.fetchStats(this.stats[stat])
    }
  },
  methods: {
    fetchStats (stat) {
      return this.$axios
        .$post(process.env.api, {
          action: 'read',
          target: 'server-status',
          name: stat.name
        })
        .then((res) => {
          const { status } = res
          stat.status = status
          if (status === 0) {
            const { version, current_players, max_players } = res
            stat.version = version
            stat.current_players = current_players
            stat.max_players = max_players
          }
        })
        .catch((reason) => { })
    }
  }
}
</script>
