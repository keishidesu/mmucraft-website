<template>
  <MCBoard>
    <MCTitle class="mt-4" style="text-shadow: 2px 6px 3px #000000;">
      {{ sectionTitle }}
    </MCTitle>
    <div class="card-body p-3 text-center">
      <div>
        {{ sectionDesc }}
      </div>
    </div>
    <hr>
  </MCBoard>
</template>

<script>
import MCBoard from '~/components/mc/mc-board'
import MCTitle from '~/components/mc/mc-title'

export default {
  components: {
    MCBoard,
    MCTitle
  },
  data: () => {
    return {
      sectionTitle: 'Joining MMUCraft',
      sectionDesc: 'Here is a step by step guide on how to join this private server. Some of the details might need your attention. Please refer back to this page or contact an admin if you encounter any problem.'
    }
  }
}
</script>

<style>

</style>
