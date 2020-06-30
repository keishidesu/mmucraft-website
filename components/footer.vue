<template>
  <b-container fluid>
    <b-row align-h="center" class="mt-4 mb-2">
      <b-col cols="12" md="8">
        <div class="p-3 bg-dark text-light text-center rounded gl-opac-80">
          MMUCraft @ {{ year }}
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
export default {
  data () {
    return {
      year: ''
    }
  },
  created () {
    this.year = new Date().getFullYear()
  }
}
</script>
