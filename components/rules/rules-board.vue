<template>
  <div class="container-fluid">
    <div class="mt-5 row justify-content-center">
      <div class="mt-5 col-12 col-md-8 position-relative text-light">
        <div class="card animated animatedFadeInUp fadeInUp bg-dark shadow-lg">
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
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { rules } from '~/assets/json/rules.json'
import MCTitle from '~/components/mc/mc-title'
import RulesCard from '~/components/rules/rules-card'

export default {
  components: {
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
