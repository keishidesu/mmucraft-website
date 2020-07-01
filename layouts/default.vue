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
  color: white;
}

.footer {
  bottom: 0;
  width: 100%;
}

.bg-none {
  background-color: rgba(255,255,255,0)
}

.gl-bg-white-10 {
  background-color: rgba(255,255,255,0.1);
}

.gl-bg-white-30 {
  background-color: rgba(255,255,255,0.3);
}

.mc-title {
  font-family: 'Bungee Inline', cursive;
  text-align: center;
}
</style>
