<template>
  <MCBoard>
    <MCTitle class="mt-4" :text-shadow="true">
      Rules and Agreements
    </MCTitle>
    <div class="text-center text-danger">
      "MMUC", "We", "Us", and "Our" refers to the team that holds responsibility in developing and maintaining the MMUC Network/Servers.
    </div>
    <hr>
    <div v-for="(rule, key) in rules" :key="`rule-${key}`" class="p-3">
      <RulesCard
        :title="key"
        :descs="rule"
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
      rules
    }
  }
}
</script>

<style>

</style>
