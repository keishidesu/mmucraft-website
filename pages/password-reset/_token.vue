<template>
  <div>
    <ResetForm :token="token" />
  </div>
</template>

<script>
import ResetForm from '~/components/password/reset-form'

export default {
  components: {
    ResetForm
  },
  asyncData ({ params, error, $axios }) {
    return $axios
      .$post(process.env.api, {
        action: 'read',
        target: 'pending',
        token: params.token || '_',
        purpose: 'password-reset'
      })
      .then((res) => {
        if (res.status === 0) {
          return { token: params.token }
        }
        error({ statusCode: 404 })
      })
      .catch((reason) => {
        error({ statusCode: 500 })
      })
  },
  data () {
    return {
      token: ''
    }
  }
}
</script>
