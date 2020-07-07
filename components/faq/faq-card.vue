<template>
  <div v-if="id">
    <h2>
      <b-button v-if="question" v-b-toggle="`collapse-${id}`" variant="light">
        {{ question }}
      </b-button>
    </h2>
    <b-collapse :id="`collapse-${id}`" accordion="my-accordion" role="tabpanel">
      <b-card class="border-0 bg-dark">
        <p v-if="answer" class="card-text" v-html="answer">
          {{ answer }}
        </p>
      </b-card>
    </b-collapse>
  </div>
</template>

<script>
export default {
  props: {
    id: {
      type: String,
      required: true
    },
    question: {
      type: String,
      required: true
    },
    answer: {
      type: String,
      required: true
    }
  }
}
</script>

<style>

</style>
