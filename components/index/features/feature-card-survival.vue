<template>
  <FeatureCards
    card-id="survival-card"
    title="Survival"
    image-url="/features/survival.png"
    :features="features"
  />
</template>

<script>
import FeatureCards from '~/components/index/features/feature-card'

export default {
  components: {
    FeatureCards
  },
  data () {
    return {
      features: [
        {
          imageUrl: '/features/survival/houses.png',
          header: 'The vanilla survival server.',
          desc: [
            'The original survival server in MMUC network.',
            'Players are free to mine and build everywhere without any restriction.',
            'Limited use of teleportation commands, things are very traditional in here.'
          ]
        },
        {
          imageUrl: '/features/survival/spread.png',
          header: 'Player spreading system.',
          desc: [
            'Spread players to a random location in a direction.',
            'Four directions and three distance to choose from.'
          ]
        },
        {
          imageUrl: '/features/survival/hell.png',
          header: 'Explore the legacies, leave your footprints and history.',
          desc: [
            'Explore old ruins, abandoned bases and crazy man-made terrains.',
            'Creates your own legends and untold stories.'
          ]
        }
      ]
    }
  }
}
</script>

<style scoped>

</style>
