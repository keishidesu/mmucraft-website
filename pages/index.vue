<template>
  <div>
    <Home />
    <Start />
    <Features />
    <Showcase />
  </div>
</template>

<script>
import Home from '~/components/index/home'
import Start from '~/components/index/start'
import Features from '~/components/index/features'
import Showcase from '~/components/index/showcase'

export default {
  components: {
    Home,
    Start,
    Features,
    Showcase
  }
}
</script>
