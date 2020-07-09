<template>
  <div class="bg-mmucraft">
    <b-container class="py-5">
      <MCTitle>
        Showcase
      </MCTitle>
      <div class="shadow mt-4">
        <b-carousel
          id="mc-carousel"
          v-model="slide"
          :interval="3000"
          controls
          indicators
          img-width="1024"
          img-height="480"
          @sliding-start="onSlideStart"
          @sliding-end="onSlideEnd"
        >
          <b-carousel-slide v-for="n in 6" :key="`screenshot-${n}`" :img-src="`/showcase/screenshot-${n}.png`" />
        </b-carousel>
      </div>
    </b-container>
  </div>
</template>

<script>
import MCTitle from '~/components/mc/mc-title'

export default {
  components: {
    MCTitle
  },
  data () {
    return {
      slide: 0,
      sliding: null
    }
  },
  methods: {
    onSlideStart (slide) {
      this.sliding = true
    },
    onSlideEnd (slide) {
      this.sliding = false
    }
  }
}
</script>
