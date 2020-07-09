<template>
  <div>
    <MCSubtitle v-if="title">
      {{ title }}
    </MCSubtitle>
    <div v-if="descs">
      <ul>
        <li v-for="desc in descs" :key="`desc-${desc}-${title}`">
          {{ desc }}
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
import MCSubtitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCSubtitle
  },
  props: {
    title: {
      type: String,
      required: true
    },
    descs: {
      type: [Object, Array],
      required: true
    }
  }
}
</script>

<style>

</style>
