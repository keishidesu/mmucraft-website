<template>
  <div>
    <script src="https://www.google.com/recaptcha/api.js?onload=vueRecaptchaApiLoaded&render=explicit" async defer />
    <div>
      <InviteForm />
    </div>
  </div>
</template>

<script>
import InviteForm from '~/components/invite/invite-form'

export default {
  components: {
    InviteForm
  }
}
</script>
