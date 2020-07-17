<template>
  <div>
    <RegisterForm :token="token" />
  </div>
</template>

<script>
import RegisterForm from '~/components/register/register-form'

export default {
  components: {
    RegisterForm
  },
  asyncData ({ params, error, $axios }) {
    return $axios
      .$post(process.env.api, {
        action: 'read',
        target: 'pending',
        token: params.token || '_',
        purpose: 'invite'
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
