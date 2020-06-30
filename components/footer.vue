<template>
  <b-container fluid>
    <div class="row justify-content-center mt-4 mb-2">
      <div class="col-12 col-md-8">
        <div class="p-3 bg-dark text-light text-center rounded gl-opac-80">
          MMUCraft @ {{ year }}
        </div>
      </div>
    </div>
  </b-container>
</template>

<script>
export default {
  created () {
    this.year = new Date().getFullYear()
  },
  data () {
    return {
      year: ''
    }
  }
}
</script>
