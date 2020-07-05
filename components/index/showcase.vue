<template>
  <div class="bg-mmucraft">
    <b-container class="py-5">
      <MCTitle>
        {{ sectionTitle }}
      </MCTitle>
      <Screenshot />
    </b-container>
  </div>
</template>

<script>
import MCTitle from '~/components/mc/mc-title'
import Screenshot from '~/components/index/screenshot'

export default {
  components: {
    MCTitle,
    Screenshot
  },
  data: () => {
    return {
      sectionTitle: 'Showcase'
    }
  }
}
</script>

<style>

</style>
