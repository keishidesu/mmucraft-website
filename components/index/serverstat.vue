<template>
  <div class="card gl-bg-white-30 rounded shadow">
    <div class="card-header text-center">
      <MCSubtitle>Server Status</MCSubtitle>
    </div>
    <b-row class="justify-content-center">
      <b-col cols="5" class="card-body text-white text-center">
        {{ name }} Server
      </b-col>
      <b-col cols="1" class="card-body text-white text-center">
        <i v-b-popover.hover.top="`${status}`" class="fa fa-circle active" />
      </b-col>
      <b-col cols="3" class="card-body text-white text-center">
        {{ current_players }} / {{ max_players }}
      </b-col>
    </b-row>
  </div>
</template>

<script>
import MCSubtitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCSubtitle
  },
  data () {
    return {
      name: 'Survival',
      max_players: '0',
      current_players: '0',
      status: 'Loading...'
    }
  }
}
</script>

<style scoped>
/*icon color to show server is active or not*/
.active {
  color:rgb(124,252,0);
}

.inactive {
  color:rgb(139,0,0);
}
</style>
