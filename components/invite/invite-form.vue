<template>
  <b-container fluid class="mt-5">
    <b-row align-h="center" class="mt-5">
      <b-col cols="12" md="6" class="mt-5 text-light">
        <b-form class="mb-5 card animated fadeInUp bg-dark shadow-lg px-5 py-5" @submit="onSubmit">
          <MCSubTitle class="text-center mb-3">
            Get Invitation
          </MCSubTitle>
          <b-form-group id="input-email" label="Email address" label-for="input-email">
            <b-form-input
              id="input-email"
              v-model="form.email"
              type="email"
              required
              placeholder="Your email"
              @keyup="onCheck()"
            />
          </b-form-group>
          <vue-recaptcha
            class="mb-3"
            theme="dark"
            :sitekey="siteKey"
            @error="recaptchaError"
            @expired="recaptchaExpired"
            @verify="recaptchaVerify"
          />
          <div>
            <b-button type="submit" variant="primary" class="d-inline mr-3" :disabled="submitDisabled">
              Get Invitation!
            </b-button>
            <span :class="{ 'text-danger': submitDisabled, 'text-success': !submitDisabled }">
              {{ submitErrorMessage }}
            </span>
          </div>
        </b-form>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import VueRecaptcha from 'vue-recaptcha'
import MCSubTitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    VueRecaptcha,
    MCSubTitle
  },
  data: () => {
    return {
      form: {
        email: '',
        token: ''
      },
      submitDisabled: true,
      submitErrorMessage: '',
      recaptchaDone: false,
      siteKey: process.env.recaptcha_key
    }
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault()
      // axios request here
    },
    onCheck () {
      // NEED FIX: Hardcoded domains, not good.
      if (!(this.form.email.endsWith('@gmail.com') || this.form.email.endsWith('@student.mmu.edu.my') || this.form.email.endsWith('@mmu.edu.my'))) {
        this.submitErrorMessage = 'Not a valid email address or a whitelisted email domain.'
        this.submitDisabled = true
        return
      }
      if (!this.recaptchaDone) {
        this.submitErrorMessage = 'Please complete the recaptcha.'
        this.submitDisabled = true
        return
      }
      this.submitErrorMessage = 'Good to go!'
      this.submitDisabled = false
    },
    recaptchaVerify (res) {
      this.form.token = res
      this.recaptchaDone = true
      this.onCheck()
    },
    recaptchaExpired () {
      this.form.token = ''
      this.recaptchaDone = false
      this.onCheck()
    },
    recaptchaError () {
      this.form.token = ''
      this.recaptchaDone = false
      this.submitDisabled = true
      this.submitErrorMessage = 'Something wrong with the recaptcha, please contact admins.'
    }
  }
}
</script>
