<template>
  <div>
    <navbar />
    <Nuxt />
    <div class="footer">
      <Footer />
    </div>
  </div>
</template>

<script>
import Navbar from '~/components/navbar'
import Footer from '~/components/footer'

export default {
  components: {
    Navbar,
    Footer
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Oswald|Patrick+Hand');
@import url('https://fonts.googleapis.com/css2?family=Bungee+Inline&display=swap');

body {
  height: 100%;
  font-family: 'Patrick Hand', cursive;
  background-image: url('~assets/img/bg-mmucraft.jpg');
  background-size: cover;
  background-attachment: fixed;
}

.footer {
  position: absolute;
  bottom: 0;
  width: 100%;
}

.mc-title {
  font-family: 'Bungee Inline', cursive;
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
