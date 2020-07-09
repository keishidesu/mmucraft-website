<template>
  <MCBoard>
    <MCTitle class="mt-4" :text-shadow="true">
      Command Guide
    </MCTitle>
    <div class="p-3">
      <div class="text-center">
        <div>
          Here are some usable commands and special prefixes that players can use in game. To use the command, type "/" in chat then follow by the command you wish.
        </div>
        <div class="mt-3">
          This
          <MCBadge content="Hover me to show an example!">
            parameter
          </MCBadge>
          represents the parameter you need to include. Hover it to view example input.
        </div>
      </div>
    </div>
    <hr>
    <div v-for="(group, g_key) in commands" :key="`group-${g_key}`" class="card-body">
      <MCSubtitle>
        {{ g_key }}
      </MCSubtitle>
      <div class="mt-3">
        <div v-for="(comm, c_key) in group" :key="`comm-${c_key}`">
          <CommandsCard
            :item="c_key"
            :usage="comm.usage"
            :parameters="comm.parameters"
            :slash="(comm.slash !== undefined) ? comm.slash : true"
          />
          <hr>
        </div>
      </div>
    </div>
  </MCBoard>
</template>

<script>
import { commands } from '~/assets/json/commands.json'
import MCBoard from '~/components/mc/mc-board'
import MCBadge from '~/components/mc/mc-badge'
import MCTitle from '~/components/mc/mc-title'
import MCSubtitle from '~/components/mc/mc-subtitle'
import CommandsCard from '~/components/commands/commands-card'

export default {
  components: {
    MCBoard,
    MCBadge,
    MCTitle,
    MCSubtitle,
    CommandsCard
  },
  data: () => {
    return {
      commands
    }
  }
}
</script>

<style>

</style>
