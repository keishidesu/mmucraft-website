<template>
  <div :class="{'text-shadow': textShadow}" class="mc-subtitle">
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
  text-shadow: 2px 2px 1.5px rgba(0, 0, 0, 1);
}

.mc-subtitle {
  font-family: 'Bungee Inline', cursive;
  font-weight: bolder;
  font-size: 1.5rem;
}
</style>
