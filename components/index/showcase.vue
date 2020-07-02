<template>
  <div class="bg-mmucraft">
    <b-container class="py-5">
      <div class="d-none d-md-block">
        <div class="mc-title text-center font-weight-bolder" style="font-size: 3rem;">
          {{ sectionTitle }}
        </div>
      </div>
      <div class="d-md-none">
        <div class="mc-title text-center font-weight-bolder" style="font-size: 1.5rem;">
          {{ sectionTitle }}
        </div>
      </div>
      <Screenshot />
    </b-container>
  </div>
</template>

<script>
import Screenshot from '~/components/index/screenshot'

export default {
  components: {
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
