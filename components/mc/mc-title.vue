<template>
  <div class="mc-title">
    <slot />
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
@media only screen and (max-width: 600px) {
  .mc-title {
    font-family: 'Bungee Inline', cursive;
    font-weight: bolder;
    font-size: 1.7rem;
    text-align: center;
  }
}

@media only screen and (min-width: 601px) {
  .mc-title {
    font-family: 'Bungee Inline', cursive;
    font-weight: bolder;
    font-size: 3rem;
    text-align: center;
  }
}
</style>
