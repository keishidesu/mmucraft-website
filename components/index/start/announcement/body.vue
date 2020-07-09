<template>
  <div class="mt-2">
    <div>
      <h4 class="text-primary d-inline">
        {{ date }}
      </h4>
      <span class="float-right">
        #{{ messageId }}
      </span>
    </div>
    <p>
      {{ content }}
    </p>
    <p class="blockquote-footer text-white gl-opac-80">
      {{ author }}
    </p>
    <hr>
  </div>
</template>

<script>
export default {
  props: {
    messageId: {
      type: String,
      required: true,
      default: ''
    },
    date: {
      type: String,
      required: true,
      default: ''
    },
    content: {
      type: String,
      required: true,
      default: ''
    },
    author: {
      type: String,
      required: true,
      default: ''
    }
  }
}
</script>
