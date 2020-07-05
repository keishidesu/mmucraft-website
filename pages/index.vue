<template>
  <div>
    <div>
      <Home />
    </div>
    <div>
      <Start />
    </div>
    <div>
      <Features />
    </div>
    <div>
      <Showcase />
    </div>
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
