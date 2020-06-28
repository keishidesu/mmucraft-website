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
</style>
