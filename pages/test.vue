<template>
  <div>
    {{ data }}
  </div>
</template>

<script>
export default {
  asyncData ({ $axios }) {
    return $axios.post('/a', { action: 'read', target: 'ping' })
      .then((res) => { return { data: res.data } })
      // eslint-disable-next-line
      .catch(err => console.log(err))
  },
  data () {
    return {
      data: undefined
    }
  }
}
</script>
