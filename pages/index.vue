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
    <div>
      <ServerInfo />
    </div>
  </div>
</template>

<script>
import Home from '~/components/index/home'
import Start from '~/components/index/start'
import Features from '~/components/index/features'
import Showcase from '~/components/index/showcase'
import ServerInfo from '~/components/index/serverinfo'

export default {
  components: {
    Home,
    Start,
    Features,
    Showcase,
    ServerInfo
  }
}
</script>
