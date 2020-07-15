<template>
  <b-container>
    <b-card class="vertical-center bg-none border-0 animated fadeInUp">
      <div class="d-none d-md-block">
        <div class="main-title font-weight-bolder" style="font-size: 6rem;">
          MMUC
        </div>
      </div>
      <div class="d-md-none">
        <div class="main-title font-weight-bolder" style="font-size: 2.8rem;">
          MMUC
        </div>
      </div>
      <div class="main-title font-weight-bolder" style="font-size: 1.3rem;">
        A minecraft network hosted by MMU Cyberjaya
      </div>
      <div class="main-title font-weight-bolder" style="font-size: 2rem;">
        <a v-b-modal.modal-online-user>
          <i class="fa fa-users" /> {{ onlineList.length }}
          <b-modal
            id="modal-online-user"
            title="Online Users"
            :hide-footer="true"
            size="md"
            header-bg-variant="dark"
            header-class="border-0"
            body-bg-variant="dark"
            centered
          >
            <MCBadge v-for="onlinePlayer in onlineList" :key="`online-player-${onlinePlayer}`">{{ onlinePlayer }}</MCBadge>
          </b-modal>
        </a>
      </div>
    </b-card>
  </b-container>
</template>

<script>
import MCBadge from '~/components/mc/mc-badge'

export default {
  components: {
    MCBadge
  },
  data () {
    return {
      onlineList: []
    }
  },
  created () {
    this.$axios
      .$post(process.env.api, {
        action: 'read',
        target: 'users-online'
      })
      .then((res) => {
        this.onlineList = res.players
      })
      .catch((reason) => { })
  }
}
</script>

<style scoped>
.vertical-center {
  padding-top: 15rem;
  padding-bottom: 15rem;
}

.main-title {
  font-family: 'Bungee Inline', cursive;
  text-shadow: 2px 6px 3px #000000;
  color: white;
  text-align: center;
}

a {
  color: rgba(255, 255, 255, .9);
  text-decoration: none;
  transition: 250ms;
}

a:hover {
  color: rgba(255, 255, 255, .95);
  text-shadow: 1px 1px 2px rgba(255, 255, 255, .3);
}
</style>
