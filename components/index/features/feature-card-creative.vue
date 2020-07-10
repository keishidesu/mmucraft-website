<template>
  <FeatureCards
    card-id="creative-card"
    title="Creative"
    image-url="/features/creative.png"
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
          imageUrl: '/features/creative/port.png',
          header: 'Free for all creative server!',
          desc: [
            'Build epic buildings with the power of WorldEdit.',
            'You are still able to collect resources anywhere else.',
            'Unlimited use of teleportation commands.'
          ]
        },
        {
          imageUrl: '/features/creative/plot.png',
          header: 'All your builds are protected.',
          desc: [
            'Everyone must claim their land before they can build.',
            'All your builds are protected in your claimed lands!',
            '16 x 16 size for each claim.'
          ]
        },
        {
          imageUrl: '/features/creative/city.png',
          header: 'The future of Creative server.',
          desc: [
            'MMU Campus builds project (Planning).',
            'Make your own minigames, parkours, etc.'
          ]
        }
      ]
    }
  }
}
</script>
