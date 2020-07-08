<template>
  <b-badge
    v-b-popover.hover.top="content"
    pill
    variant="info"
    class="pointer mx-1"
    data-placement="top"
  >
    <slot />
  </b-badge>
</template>

<script>
export default {
  props: {
    content: {
      type: String,
      required: true,
      default: ''
    }
  }
}
</script>

<style scoped>
  .pointer {
    cursor: pointer;
  }
</style>
