<template>
  <div class="container-fluid mt-5">
    <div class="mt-5 row justify-content-center">
      <div class="mt-5 col-6 position-relative text-light">
        <div class="card animated fadeInUp bg-dark shadow-lg">
          <MCSubTitle class="text-center p-1">
            {{ sectionTitle }}
          </MCSubTitle>
        </div>
        <br>
        <b-form class="mb-5 card animated fadeInUp bg-dark shadow-lg px-5 py-5" @submit="onSubmit">
          <b-form-group id="input-group-1" label="MMU Email address:" label-for="input-1">
            <b-form-input id="input-1" v-model="form.email" type="email" required placeholder="Enter email" />
          </b-form-group>
          <b-form-group id="input-group-2" label="Previous Password:" label-for="input-2">
            <b-form-input id="input-2" v-model="form.prevpwd" type="password" required placeholder="Enter old password" />
          </b-form-group>
          <b-form-group id="input-group-3" label="New Password:" label-for="input-3">
            <b-form-input id="input-3" v-model="form.newpwd1" type="password" required placeholder="Enter new password" />
          </b-form-group>
          <b-form-group id="input-group-4" label="Confirm Password:" label-for="input-4">
            <b-form-input id="input-4" v-model="form.newpwd2" type="password" required placeholder="Re-enter new password" />
          </b-form-group>
          <div>
            <b-button type="submit" variant="primary">
              submit
            </b-button>
          </div>
        </b-form>
      </div>
    </div>
  </div>
</template>

<script>
import MCSubTitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCSubTitle
  },
  data: () => {
    return {
      form: {
        email: '',
        prevpwd: '',
        newpwd1: '',
        newpwd2: ''
      },
      sectionTitle: 'Forgot Password'
    }
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault()
      if (this.form.newpwd1 !== this.form.newpwd2) {
        alert('Passwords does not match.')
      } else if (this.form.prevpwd === this.form.newpwd1) {
        alert('New password can not be same as previous password.')
      } else {
        alert(JSON.stringify(this.form))
      }
    }
  }
}
</script>
