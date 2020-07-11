<template>
  <div class="container-fluid mt-5">
    <div class="mt-5 row justify-content-center">
      <div class="mt-5 col-6 position-relative text-light">
        <div class="card animated fadeInUp bg-dark shadow-lg">
          <MCSubTitle style="text-align:center; padding:1rem;">
            {{ sectionTitle }}
          </MCSubTitle>
        </div>
        <br>
        <div class="mb-5 card animated fadeInUp bg-dark shadow-lg px-5 py-5">
          <h6>MMU Email Address</h6>
          <b-form-input v-model="email" placeholder="Enter email" />
          <br>
          <h6>Previous Password</h6>
          <b-form-input v-model="prevpwd" type="password" placeholder="Enter old password" />
          <br>
          <h6>New Password</h6>
          <b-form-input v-model="newpwd1" type="password" placeholder="Enter new password" />
          <br>
          <h6>Confirm Password</h6>
          <b-form-input v-model="newpwd2" type="password" placeholder="Re-Enter new password" />
          <br>
          <div>
            <b-button variant="primary" :disabled="isDisabled">
              submit
            </b-button>
          </div>
        </div>
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
      email: '',
      prevpwd: '',
      newpwd1: '',
      newpwd2: '',
      sectionTitle: 'Forgot Password'
    }
  },
  computed: {
    isDisabled () {
      if (this.prevpwd !== this.newpwd1 && this.newpwd1 !== '' && this.newpwd2 !== '') {
        if (this.newpwd1 === this.newpwd2) {
          return false
        }
      }
      return true
    }
  }
}
</script>
