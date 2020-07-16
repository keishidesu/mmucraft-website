<template>
  <MCBoard>
    <MCTitle class="mt-4" style="text-shadow: 2px 6px 3px #000000;">
      {{ sectionTitle }}
    </MCTitle>
    <hr>
    <div class="card-body" style="padding:1rem">
      <b-form @submit="onSubmit">
        <b-form-group
          id="input-group-1"
          label="MMU email address"
          label-for="input-1"
          description="MMU email is required to send the invitation link"
        >
          <b-form-input
            id="input-1"
            v-model="form.email"
            type="email"
            required
            placeholder="Enter email"
          />
        </b-form-group>
        <vue-recaptcha sitekey="site-key" />
        <br>
        <b-button type="submit" variant="primary">
          Send Invitation
        </b-button>
      </b-form>
    </div>
  </MCBoard>
</template>

<script>
import VueRecaptcha from 'vue-recaptcha'
import MCBoard from '~/components/mc/mc-board'
import MCTitle from '~/components/mc/mc-title'

export default {
  components: {
    MCBoard,
    MCTitle,
    VueRecaptcha
  },
  data () {
    return {
      form: {
        email: ''
      },
      sectionTitle: 'Get Invitation'
    }
  },
  methods: {
    onSubmit (evt) {
      evt.preventDefault()
      alert(JSON.stringify(this.form))
    }
  }
}
</script>
