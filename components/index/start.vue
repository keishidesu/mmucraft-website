<template>
  <div class="bg-dark">
    <b-container class="py-5 animated fadeInUp">
      <MCTitle>
        <a v-b-toggle.collapse-start>
          Getting Started
        </a>
      </MCTitle>
      <b-collapse id="collapse-start">
        <b-card class="border-0 bg-none text-center">
          <div>
            MMUC Network is an offline-mode Minecraft server that contains various game modes.
          </div>
        </b-card>
      </b-collapse>
      <div>
        <StartCard />
      </div>
      <b-row class="mt-5">
        <Anouncement />
        <b-col cols="12" lg="4" class="mt-3">
          <ServerStat />
          <Github />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import MCTitle from '~/components/mc/mc-title'
import StartCard from '~/components/index/start/start-cards'
import Anouncement from '~/components/index/start/anouncement'
import Github from '~/components/index/start/github'
import ServerStat from '~/components/index/start/serverstat'

export default {
  components: {
    MCTitle,
    StartCard,
    Anouncement,
    Github,
    ServerStat
  }
}
</script>

<style scoped>
a {
  cursor: pointer;
  transition: 250ms;
}

a:hover {
  text-shadow: 1px 1px 2px rgba(255, 255, 255, .5);
}
</style>
