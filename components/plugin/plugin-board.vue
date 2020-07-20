<template>
  <MCBoard>
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
          <div
            :is="plugin.tag"
            :href="plugin.href ? plugin.href : ''"
            target="_blank"
          >
            {{ plugin.text }}
          </div>
        </li>
      </ul>
    </div>
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
  text-decoration: none;
  cursor: pointer;
}

element {

}
</style>
