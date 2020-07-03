<template>
  <div class="bg-mmucraft">
    <b-container class="py-5">
      <div class="d-none d-md-block">
        <MCTitle>
          {{ sectionTitle }}
        </MCTitle>
      </div>
      <div class="d-md-none">
        <MCSubtitle class="text-center">
          {{ sectionTitle }}
        </MCSubtitle>
      </div>
      <Screenshot />
    </b-container>
  </div>
</template>

<script>
import MCTitle from '~/components/mc/mc-title'
import MCSubtitle from '~/components/mc/mc-subtitle'
import Screenshot from '~/components/index/screenshot'

export default {
  components: {
    MCTitle,
    MCSubtitle,
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
