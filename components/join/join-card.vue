<template>
  <div class="p-3">
    <MCSubtitle>
      {{ (cardId + 1) }} - {{ title }}
    </MCSubtitle>
    <div v-for="(item, i) in desc" :key="`join-desc-${cardId}-${i}`" class="mt-3">
      <div v-if="item.tag === 'button'">
        <b-button :href="item.href" variant="light">
          {{ item.text }}
        </b-button>
      </div>
      <div v-else-if="item.tag === 'quote'" class="py-1">
        <span class="p-2 quote rounded text-info">
          {{ item.text }}
        </span>
      </div>
      <component :is="item.tag" v-else :class="`text-${item.variant || 'light' }`">
        {{ item.text }}
      </component>
    </div>
    <hr>
  </div>
</template>

<script>
import MCSubtitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCSubtitle
  },
  props: {
    cardId: {
      type: Number,
      required: true,
      default: 0
    },
    title: {
      type: String,
      required: true,
      default: ''
    },
    desc: {
      type: Array,
      required: true,
      default: () => []
    }
  }
}
</script>

<style scoped>
.quote {
  background-color: rgba(0, 0, 0, .25);
  border-left: 5px solid rgba(255, 255, 255, .25);
}
</style>
