<template>
  <b-container>
    <b-card class="vertical-center bg-none border-0">
      <div class="d-none d-md-block">
        <div class="main-title font-weight-bolder" style="font-size: 6rem;">
          MMUCRAFT
        </div>
      </div>
      <div class="d-md-none">
        <div class="main-title font-weight-bolder" style="font-size: 2.8rem;">
          MMUCRAFT
        </div>
      </div>
      <div class="main-title font-weight-bolder" style="font-size: 1.3rem;">
        A private minecraft server for MMU
      </div>
      <div class="main-title font-weight-bolder" style="font-size: 2rem;">
        <i class="fa fa-users" /> {{ users_online }}
      </div>
    </b-card>
  </b-container>
</template>

<script>

export default {
  data () {
    return {
      users_online: '0'
    }
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
