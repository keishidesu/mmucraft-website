<template>
  <div class="bg-dark">
    <b-container class="py-5">
      <div class="d-none d-md-block">
        <MCTitle>
          {{ sectionTitle }}
          <b-button v-b-toggle.collapse-start variant="outline-light" class="m-1">
            <i class="fa fa-chevron-down" />
          </b-button>
        </MCTitle>
      </div>
      <div class="d-md-none">
        <MCSubtitle class="text-center">
          {{ sectionTitle }}
          <b-button v-b-toggle.collapse-start variant="outline-light" class="m-1">
            <i class="fa fa-chevron-down" />
          </b-button>
        </MCSubtitle>
      </div>
      <b-collapse id="collapse-start">
        <b-card class="border-0 bg-none text-center">
          <div>
            {{ desc }}
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
import MCSubtitle from '~/components/mc/mc-subtitle'
import StartCard from '~/components/index/start-cards'
import Anouncement from '~/components/index/anouncement'
import Github from '~/components/index/github'
import ServerStat from '~/components/index/serverstat'

export default {
  components: {
    MCTitle,
    MCSubtitle,
    StartCard,
    Anouncement,
    Github,
    ServerStat
  },
  data: () => {
    return {
      sectionTitle: 'Getting Started',
      desc: 'MMUCraft is an offline-mode Minecraft server which allows cracked Minecraft clients to join. This is server for players to enjoy the original survival game of Minecraft. Join us with your friends now!'
    }
  }
}
</script>

<style>

</style>
