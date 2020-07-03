<template>
  <div class="bg-mmucraft">
    <b-container class="py-5">
      <MCTitle>
        {{ sectionTitle }}
      </MCTitle>
    </b-container>
  </div>
</template>

<script>
import MCTitle from '~/components/mc/mc-title'

export default {
  components: {
    MCTitle
  },
  data: () => {
    return {
      sectionTitle: 'Features'
    }
  }
}
</script>

<style>

</style>
