<template>
  <b-container>
    <b-row class="mt-5" align-h="center">
      <b-col cols="12" md="8" class="mt-5 text-center">
        <div class="p-3 box rounded">
          <MCSubtitle class="mt-3" :text-shadow="true">
            Oh no! You just got a...
          </MCSubtitle>
          <MCTitle class="my-3 big-text" :text-shadow="true">
            {{ error.statusCode }}
          </MCTitle>
          <MCSubtitle class="mb-3" :text-shadow="true">
            <a target="_blank" :href="`https://www.google.com/search?q=${error.statusCode}+http+status+code`">
              Click here to find out what it is!
            </a>
          </MCSubtitle>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import MCTitle from '~/components/mc/mc-title'
import MCSubtitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCTitle,
    MCSubtitle
  },
  props: {
    error: {
      type: Object,
      required: true,
      default: () => {}
    }
  }
}
</script>

<style scoped>
a {
  color: rgba(255, 255, 255, 1);
  transition: 250ms;
}

a:hover {
  color: rgba(255, 255, 255, 1);
  text-shadow: 1px 1px 2px rgba(255, 255, 255, .5);
  text-decoration: none;
}

.box {
  background-color: rgba(0, 0, 0, .5);
}

.big-text {
  font-size: 4.5rem;
}
</style>
