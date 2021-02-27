<template>
  <b-container fluid class="mt-5">
    <b-row align-h="center" class="mt-5">
      <b-col cols="12" md="6" class="mt-5 text-light">
        <b-form class="mb-5 card animated fadeInUp bg-dark shadow-lg px-5 py-5" method="POST" @submit="onSubmit">
          <MCSubTitle class="text-center mb-3">
            Password Reset
          </MCSubTitle>
          <div class="text-danger">
            Please report to admins if you do not request for this and close this page immediately.
          </div>
          <b-form-group id="input-password" label="Password" label-for="input-password">
            <b-form-input
              id="input-password"
              v-model="form.password"
              type="password"
              required
              placeholder="Your new password"
              @keyup="onCheck()"
            />
          </b-form-group>
          <b-form-group id="input-compassword" label="Comfirm password" label-for="input-compassword">
            <b-form-input
              id="input-compassword"
              v-model="form.comfirmpassword"
              type="password"
              required
              placeholder="Type your password again"
              @keyup="onCheck()"
            />
          </b-form-group>
          <div>
            <b-button type="submit" variant="primary" class="d-inline mr-3" :disabled="submitDisabled">
              <span v-if="!loading">
                Reset!
              </span>
              <b-spinner v-else variant="light" />
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
import MCSubTitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCSubTitle
  },
  props: {
    token: {
      type: String,
      required: true,
      default: ''
    }
  },
  data: () => {
    return {
      form: {
        password: '',
        comfirmpassword: ''
      },
      submitDisabled: true,
      submitErrorMessage: '',
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
          action: 'update',
          target: 'password-reset',
          password: this.form.password,
          token: this.token
        })
        .then((res) => {
          if (res.status === 0) {
            this.makeToast('Your password has been updated!')
            setTimeout(() => {
              this.$router.push('/')
            }, 3000)
          } else if (res.status === 1) {
            this.makeToast('Invitation token missing! Please contact admin.', true)
            setTimeout(() => {
              this.$router.push('/')
            }, 3000)
          } else if (res.status === 2) {
            this.makeToast('Password too short.', true)
          } else if (res.status === 3) {
            this.makeToast('User not exist, please contact admin!', true)
            setTimeout(() => {
              this.$router.push('/')
            }, 3000)
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
          this.form.password = ''
          this.form.comfirmpassword = ''
          this.onCheck()
        })
    },
    onCheck () {
      if (this.form.password.length < 5) {
        this.submitErrorMessage = 'Password must contains at least 5 characters.'
        this.submitDisabled = true
        return
      }
      if (this.form.password !== this.form.comfirmpassword) {
        this.submitErrorMessage = 'Confirm password does not match.'
        this.submitDisabled = true
        return
      }
      this.submitErrorMessage = 'Alright, make sure you remember your new password!'
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
    }
  }
}
</script>
