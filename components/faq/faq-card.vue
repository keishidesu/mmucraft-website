<template>
  <div v-if="id">
    <a v-if="question" v-b-toggle="id">
      <span class="when-closed mr-2">
        +
      </span>
      <span class="when-opened mr-2">
        -
      </span>
      {{ question }}
    </a>
    <b-collapse :id="id" :accordion="accordion" role="tabpanel">
      <b-card class="border-0 bg-dark">
        <div v-if="answer">
          <component
            :is="item.tag"
            v-for="(item, i) in answer"
            :key="`faq-questions-${i}`"
            :href="item.href ? item.href : ''"
            target="_blank"
          >
            {{ item.text }}
          </component>
        </div>
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
      type: Array,
      required: true
    },
    accordion: {
      type: String,
      required: true
    }
  }
}
</script>

<style scoped>
a {
  text-decoration: none;
  cursor: pointer;
  color: rgba(255, 255, 255, 1);
}
.collapsed > .when-opened {
  display: none;
}

.not-collapsed > .when-closed {
  display: none;
}
</style>
