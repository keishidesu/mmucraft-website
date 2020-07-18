<template>
  <div>
    <InviteForm />
  </div>
</template>

<script>
import InviteForm from '~/components/invite/invite-form'

export default {
  components: {
    InviteForm
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
