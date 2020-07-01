<template>
  <div class="bg-mmucraft">
    <b-container class="py-5">
      <div class="d-none d-md-block">
        <div class="mc-title font-weight-bolder" style="font-size: 3rem;">
          {{ sectionTitle }}
        </div>
      </div>
      <div class="d-md-none">
        <div class="mc-title font-weight-bolder" style="font-size: 1.5rem;">
          {{ sectionTitle }}
        </div>
      </div>
    </b-container>
    <FeatureCards />
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      sectionTitle: 'Features'
    }
  }
}
</script>

<style>
.bg-mmucraft {
  background-image:url('~assets/img/bg-features.jpg');
  background-size: cover;
  background-attachment: fixed;
}
</style>
