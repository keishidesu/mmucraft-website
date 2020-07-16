<template>
  <div class="container-fluid mt-5">
    <div class="mt-5 row justify-content-center">
      <div class="mt-5 col-6 position-relative text-light">
        <div class="card animated fadeInUp bg-dark shadow-lg">
          <MCSubTitle class="text-center p-1">
            Register
          </MCSubTitle>
        </div>
        <br>
        <b-form class="mb-5 card animated fadeInUp bg-dark shadow-lg px-5 py-5" @submit="onSubmit">
          <b-form-group id="input-ign" label="In-game-name" label-for="input-ign">
            <b-form-input id="input-ign" v-model="form.ingamename" type="text" required placeholder="In-game-name" />
          </b-form-group>
          <b-form-group id="input-password" label="Password:" label-for="input-password">
            <b-form-input id="input-password" v-model="form.password" type="password" required placeholder="New password" />
          </b-form-group>
          <b-form-group id="input-compassword" label="Comfirm password:" label-for="input-compassword">
            <b-form-input id="input-compassword" v-model="form.comfirmpassword" type="password" required placeholder="Comfirmed password" />
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
        ingamename: '',
        password: '',
        comfirmpassword: ''
      }
    }
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault()
      if (this.form.password !== this.form.comfirmpassword) {
        alert('Passwords does not match.')
      } else {
        alert(JSON.stringify(this.form))
      }
    }
  }
}
</script>
