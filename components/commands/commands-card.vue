<template>
  <div>
    <div v-if="item">
      <div v-if="parameters">
        /{{ item }}
        <MCBadge
          v-for="para in parameters"
          :key="`para-${para}-${item}`"
          :title="`${para.example}`"
          class="mt-2"
        >
          {{ para.name }}
        </MCBadge>
      </div>
      <div class="usage mt-2">
        {{ usage }}
      </div>
    </div>
  </div>
</template>

<script>
import MCBadge from '~/components/mc/mc-badge'

export default {
  components: {
    MCBadge
  },
  props: {
    item: {
      type: String,
      required: true
    },
    usage: {
      type: String,
      required: true
    },
    parameters: {
      type: [Object, Array],
      required: false,
      default () {}
    }
  }
}
</script>

<style scoped>
.usage {
  color: rgba(255,255,255,0.6)
}
</style>
