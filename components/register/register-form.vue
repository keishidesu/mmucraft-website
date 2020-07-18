<template>
  <b-container fluid class="mt-5">
    <b-row align-h="center" class="mt-5">
      <b-col cols="12" md="6" class="mt-5 text-light">
        <b-form class="mb-5 card animated fadeInUp bg-dark shadow-lg px-5 py-5" @submit="onSubmit">
          <MCSubTitle class="text-center mb-3">
            Register
          </MCSubTitle>
          <div class="text-danger">
            <div>
              If you did not request for this please leave this page.
            </div>
            <div>
              In-game name is NOT your Minecraft username! Please match it with the name where other sees in the game!
            </div>
          </div>
          <b-form-group id="input-ign" label="In-game name" label-for="input-ign">
            <b-form-input
              id="input-ign"
              v-model="form.ingamename"
              type="text"
              required
              placeholder="Your in-game name"
              @keyup="onCheck()"
            />
          </b-form-group>
          <b-form-group id="input-password" label="Password" label-for="input-password">
            <b-form-input
              id="input-password"
              v-model="form.password"
              type="password"
              required
              placeholder="Your password"
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
                Register Me!
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
        ingamename: '',
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
          action: 'create',
          target: 'user',
          name: this.form.ingamename,
          password: this.form.password,
          token: this.token
        })
        .then((res) => {
          if (res.status === 0) {
            this.makeToast('You have successfully registered an account!')
            setTimeout(() => {
              this.$router.push('/')
            }, 3000)
          } else if (res.status === 1) {
            this.makeToast('Invitation token missing! Please contact admin.', true)
            setTimeout(() => {
              this.$router.push('/')
            }, 3000)
          } else if (res.status === 2) {
            this.makeToast('Invalid username.', true)
          } else if (res.status === 3) {
            this.makeToast('The username or email has been taken.', true)
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
          this.form.ingamename = ''
          this.form.password = ''
          this.form.comfirmpassword = ''
          this.onCheck()
        })
    },
    onCheck () {
      if (!/^[A-Za-z0-9_]+$/.test(this.form.ingamename) || this.form.ingamename.length < 3 || this.form.ingamename.length > 16) {
        this.submitErrorMessage = 'Invalid name. Length must between 3 to 16. Can only contains letters, numbers and underscore.'
        this.submitDisabled = true
        return
      }
      if (this.form.password === '') {
        this.submitErrorMessage = 'Password required'
        this.submitDisabled = true
        return
      }
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
    }
  }
}
</script>
