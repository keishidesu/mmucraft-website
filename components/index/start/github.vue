<template>
  <div class="card gl-bg-white-30 mt-3 rounded shadow">
    <div class="card-header text-center">
      <MCSubtitle>Repositories</MCSubtitle>
    </div>
    <div class="card-body text-white text-center">
      <b-img src="/getstart/github.png" />
      <b-row
        v-for="(item,i) in items"
        :key="`item-${i}`"
        class="mt-3 justify-content-center text-left"
      >
        <b-col class="mr-2">
          <a :href="item.link" target="_blank">
            <b-img :src="`/getstart/${item.image}.png`" class="mx-5 d-inline icon" />
            <h3 class="d-inline">
              {{ item.title }}
            </h3>
          </a>
        </b-col>
      </b-row>
    </div>
  </div>
</template>

<script>
import MCSubtitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCSubtitle
  },
  data: () => {
    return {
      items: [
        {
          image: 'diamond',
          title: 'Website',
          link: 'https://github.com/keishidesu/mmucraft-website'
        },
        {
          image: 'book',
          title: 'API',
          link: 'https://github.com/Tajam/mmucraft-api'
        },
        {
          image: 'bot',
          title: 'Discord Bot',
          link: 'https://github.com/Tajam/mmucraft-discord-bot'
        }
      ]
    }
  }
}
</script>

<style scoped>
a {
  color: rgba(255, 255, 255, .9);
  text-decoration: none;
  transition: 250ms;
}

a:hover {
  color: rgba(255, 255, 255, .95);
  text-shadow: 1px 1px 2px rgba(255, 255, 255, .6);
}

</style>
