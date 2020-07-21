<template>
  <MCBoard>
    <b-row align-h="center">
      <b-col cols="12" md="8">
        <MCTitle>
          Plugins
        </MCTitle>
        <div>
          <ul>
            <li
              v-for="plugin in plugins"
              :key="`plugin-${plugin}`"
              class="my-1"
            >
              <a
                :href="plugin.href ? plugin.href : ''"
                target="_blank"
              >
                {{ plugin.text }}
              </a>
            </li>
          </ul>
        </div>
      </b-col>
    </b-row>
  </MCBoard>
</template>

<script>
import MCBoard from '~/components/mc/mc-board'
import MCTitle from '~/components/mc/mc-title'
import { plugins } from '~/assets/json/plugins.json'

export default {
  components: {
    MCBoard,
    MCTitle
  },
  data: () => {
    return {
      plugins
    }
  }
}
</script>

<style scoped>
ul {
  columns: 2;
  -webkit-columns: 2;
  -moz-columns: 2;
}

a {
  color: rgba(255, 255, 255, 1);
  transition: 250ms;
}

a:hover {
  text-shadow: 1px 1px 2px rgba(255, 255, 255, .5);
  text-decoration: none;
  cursor: pointer;
}
</style>
