<template>
  <div>
    <navbar />
    <Nuxt />
    <div>
      <MCDiscord />
    </div>
    <div class="footer">
      <Footer />
    </div>
  </div>
</template>

<script>
import Navbar from '~/components/navbar'
import Footer from '~/components/footer'
import MCDiscord from '~/components/mc/mc-discordbtn'

export default {
  components: {
    Navbar,
    Footer,
    MCDiscord
  }
}
</script>

<style>
body {
  height: 100%;
  font-family: 'Patrick Hand', cursive;
  background-image: url('~assets/img/bg-mmucraft.jpg');
  background-size: cover;
  background-attachment: fixed;
  color: white;
}

.footer{
  bottom: 0;
  width: 100%;
  opacity: 0.7;
}

.bg-none {
  background-color: rgba(255,255,255,0)
}

.bg-mmucraft {
  background-image:url('~assets/img/bg-features.jpg');
  background-size: cover;
  background-attachment: fixed;
}

.gl-bg-white-10 {
  background-color: rgba(255,255,255,0.1);
}

.gl-bg-white-30 {
  background-color: rgba(255,255,255,0.3);
}

/* Animation */
@keyframes fadeInUp {
  from {
    transform: translate3d(0,40px,0)
  }

  to {
    transform: translate3d(0,0,0);
  }
}

@-webkit-keyframes fadeInUp {
  from {
    transform: translate3d(0,40px,0)
  }

  to {
    transform: translate3d(0,0,0);
  }
}

.animated {
  animation-duration: 1.3s;
  animation-fill-mode: both;
  -webkit-animation-duration: 1.3s;
  -webkit-animation-fill-mode: both
}

.fadeInUp {
  animation-name: fadeInUp;
  -webkit-animation-name: fadeInUp;
}
</style>
