<template>
  <MCBoard>
    <MCTitle class="mt-4" :text-shadow="true">
      Joining MMUC Network
    </MCTitle>
    <div class="p-3 text-center">
      <span>
        Here is a step by step guide on how to join this private server. Some of the details might need your attention. Please refer back to this page or
      </span>
      <a target="_blank" class="mx-1" href="https://discord.gg/jMtqPjH">
        contact
      </a>
      <span>
        an admin if you encounter any problem.
      </span>
    </div>
    <hr>
    <JoinCard
      v-for="(item, i) in join"
      :key="`join-card-${i}`"
      :card-id="i"
      :title="item.title"
      :desc="item.desc"
    />
  </MCBoard>
</template>

<script>
import { join } from '~/assets/json/join.json'
import MCBoard from '~/components/mc/mc-board'
import MCTitle from '~/components/mc/mc-title'
import JoinCard from '~/components/join/join-card'

export default {
  components: {
    MCBoard,
    MCTitle,
    JoinCard
  },
  data: () => {
    return {
      join
    }
  }
}
</script>
