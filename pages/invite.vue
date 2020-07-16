<template>
  <div>
    <script src="https://www.google.com/recaptcha/api.js?onload=vueRecaptchaApiLoaded&render=explicit" async defer />
    <div>
      <Form />
    </div>
  </div>
</template>

<script>
import Form from '~/components/invite/form'

export default {
  components: {
    Form
  }
}
</script>
