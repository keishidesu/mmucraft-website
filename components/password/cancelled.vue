<template>
  <MCBoard>
    <MCSubtitle class="text-center mt-4" :text-shadow="true">
      Password Reset Request Cancelled
    </MCSubtitle>
    <div class="text-center mb-3">
      Refresh this page should direct you to a 404 page.
    </div>
  </MCBoard>
</template>

<script>
import MCBoard from '~/components/mc/mc-board'
import MCSubtitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCBoard,
    MCSubtitle
  }
}
</script>

<style>

</style>
