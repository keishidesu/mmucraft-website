<template>
  <b-row class="justify-content-center">
    <b-col
      v-for="(card,i) in cards"
      :key="`card-${i}`"
      cols="11"
      lg="4"
    >
      <div class="mt-4">
        <a v-b-modal="`modal${i}`">
          <div class="card feature-hover shadow-lg border-0 border-round">
            <img class="img-fluid card-img feature-hover" :src="`/features/${card.image}.png`" :alt="`${card.title}`">
            <div class="card-img-overlay d-flex">
              <div class="my-auto mx-auto text-center">
                <MCSubtitle class="card-title" style="text-shadow: 2px 6px 3px #000000;">
                  {{ card.title }}
                </MCSubtitle>
              </div>
            </div>
          </div>
        </a>
      </div>
      <b-modal
        :id="`modal${i}`"
        :title="`${card.title} World`"
        :header-bg-variant="headerBgVariant"
        :body-bg-variant="bodyBgVariant"
        :footer-bg-variant="footerBgVariant"
        centered
        ok-only
        ok-variant="secondary"
        ok-title="Ok"
      >
        <div v-for="modal in card.modals" :key="`desc-${modal}-${i}`">
          <p class="my-1">
            {{ modal }}
          </p>
        </div>
      </b-modal>
    </b-col>
  </b-row>
</template>

<script>
import MCSubtitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCSubtitle
  },
  data: () => {
    return {
      cards: [
        {
          id: '1',
          image: 'survival',
          title: 'Survival',
          modals: [
            'Card text in here',
            'another text'
          ]
        },
        {
          id: '2',
          image: 'creative',
          title: 'Creative',
          modals: [
            'Card text in here'
          ]
        },
        {
          id: '3',
          image: 'civil',
          title: 'Civil',
          modals: [
            'Card text in here'
          ]
        }
      ],
      variants: ['dark'],
      headerBgVariant: 'dark',
      bodyBgVariant: 'dark',
      footerBgVariant: 'dark'
    }
  }
}
</script>

<style scoped>
a a:hover{
  text-decoration: none;
}

.feature-hover:hover {
  opacity: 0.8;
  transition: 0.2s;
}
</style>
