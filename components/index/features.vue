<template>
  <div class="bg-mmucraft">
    <b-container class="py-5">
      <MCTitle>
        {{ sectionTitle }}
      </MCTitle>
      <FeatureCards />
    </b-container>
  </div>
</template>

<script>
import MCTitle from '~/components/mc/mc-title'
import FeatureCards from '~/components/index/feature-cards'

export default {
  components: {
    MCTitle,
    FeatureCards
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
