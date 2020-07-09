<template>
  <div :class="{'text-shadow': textShadow}" class="mc-title">
    <slot />
  </div>
</template>

<script>
export default {
  props: {
    textShadow: {
      type: Boolean,
      required: false,
      default: false
    }
  }
}
</script>

<style scoped>
.text-shadow {
  text-shadow: 2px 6px 3px rgba(0, 0, 0, 1);
}

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
