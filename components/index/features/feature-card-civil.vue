<template>
  <FeatureCards
    card-id="civil-card"
    title="Civil"
    image-url="/features/civil.png"
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
          imageUrl: '/features/civil/market.png',
          header: 'A Survival Server that offers grief protection.',
          desc: [
            'Claim lands and stay protected from griefing.',
            'You are still able to collect resources anywhere else.',
            'Unlimited use of teleport to player, back to death position and back to home command!'
          ]
        },
        {
          imageUrl: '/features/civil/house.png',
          header: 'More to come!',
          desc: [
            'Civil server is still very new to us.',
            'We will have more features in the future!'
          ]
        }
      ]
    }
  }
}
</script>
