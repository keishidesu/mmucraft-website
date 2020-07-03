<template>
  <MCBoard>
    <MCTitle class="mt-4" style="text-shadow: 2px 6px 3px #000000;">
      {{ sectionTitle }}
    </MCTitle>
    <div class="card-body p-3">
      <div class="text-center text-danger" style="font-size:1.1rem">
        Any action performed by any player that any admin consider as a threat to community and server will result in permanent ban.<br>
        Think of yourself and behave. Report to us if you found any harmful player.
      </div>
    </div>
    <hr>
    <div v-for="(rule, key) in rules" :key="`rule-${key}`" class="card-body">
      <RulesCard
        :title="rule.title"
        :descs="rule.descs"
      />
      <hr>
    </div>
  </MCBoard>
</template>

<script>
import { rules } from '~/assets/json/rules.json'
import MCBoard from '~/components/mc/mc-board'
import MCTitle from '~/components/mc/mc-title'
import RulesCard from '~/components/rules/rules-card'

export default {
  components: {
    MCBoard,
    MCTitle,
    RulesCard
  },
  data: () => {
    return {
      rules,
      sectionTitle: 'Server Rules'
    }
  }
}
</script>

<style>

</style>
