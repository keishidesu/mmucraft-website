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
        <i class="fa fa-users" /> {{ onlineList.length }}
      </div>
    </b-card>
  </b-container>
</template>

<script>

export default {
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
</style>
