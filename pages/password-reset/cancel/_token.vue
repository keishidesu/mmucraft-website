<template>
  <div>
    <Cancelled :email="email" />
  </div>
</template>

<script>
import Cancelled from '~/components/password/cancelled'

export default {
  components: {
    Cancelled
  },
  asyncData ({ params, error, $axios }) {
    return $axios
      .$post(process.env.api, {
        action: 'delete',
        target: 'pending-token',
        token: params.token || '_',
        purpose: 'password-reset'
      })
      .then((res) => {
        if (res.status === 0) {
          return { email: params.email }
        }
        error({ statusCode: 404 })
      })
      .catch((reason) => {
        error({ statusCode: 500 })
      })
  },
  data () {
    return {
      email: ''
    }
  }
}
</script>
