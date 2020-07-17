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
              <span v-if="!loading">
                {{ submitErrorMessage }}
              </span>
              <b-spinner v-else small variant="light" />
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
      siteKey: process.env.recaptcha_key,
      loading: false
    }
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault()
      this.loading = true
      this.submitDisabled = true
      this.$axios
        .$post(process.env.api, {
          action: 'create',
          target: 'pending-invite',
          email: this.form.email,
          token: this.form.token
        })
        .then((res) => {
          if (res.status === 0) {
            this.makeToast('An invitation is on the way to your mail box. Might need to take up to 10 minutes to arrive!')
            setTimeout(() => {
              this.$router.push('/')
            }, 4000)
          } else if (res.status === 1) {
            this.makeToast('Invalid email address.', true)
          } else if (res.status === 2) {
            this.makeToast('Recaptcha failed, please try again.', true)
          } else if (res.status === 3) {
            this.makeToast('This email address has been taken.', true)
          } else if (res.status === 4) {
            this.makeToast('For some reason we cannot send you the invitation, please contact admin for help.', true)
          } else {
            this.makeToast('Unknown error.', true)
          }
        })
        .catch((reason) => {
          this.makeToast('Internal error! please contact admin.', true)
          setTimeout(() => {
            this.$router.push('/')
          }, 3000)
        })
        .finally(() => {
          this.loading = false
          this.form.email = ''
          this.form.token = ''
          this.onCheck()
        })
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
    makeToast (message, error) {
      this.$bvToast.toast(message, {
        title: error ? 'Error!' : 'Okay!',
        variant: error ? 'danger' : 'success',
        toaster: 'b-toaster-top-center',
        solid: false,
        appendToast: false
      })
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
