<template>
  <MCBoard>
    <MCTitle class="mt-4" :text-shadow="true">
      Plugins
    </MCTitle>
    <div>
      <ul>
        <li v-for="plugin in plugins" :key="plugin">
          <p>
            {{ plugin }}
          </p>
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
