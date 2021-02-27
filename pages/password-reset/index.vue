<template>
  <div>
    <RequestForm />
  </div>
</template>

<script>
import RequestForm from '~/components/password/request-form'

export default {
  components: {
    RequestForm
  },
  head () {
    return {
      script: [
        {
          src: 'https://www.google.com/recaptcha/api.js?onload=vueRecaptchaApiLoaded&render=explicit',
          async: true,
          defer: true
        }
      ]
    }
  }
}
</script>
