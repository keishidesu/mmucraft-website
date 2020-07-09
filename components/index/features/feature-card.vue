<template>
  <div class="mt-4">
    <a v-b-modal="`feature-card-modal-${cardId}`">
      <div class="card feature-hover shadow-lg border-0 border-round">
        <img class="img-fluid card-img feature-hover" :src="imageUrl">
        <div class="card-img-overlay d-flex">
          <div class="my-auto mx-auto text-center">
            <MCSubtitle class="card-title" :text-shadow="true">
              {{ title }}
            </MCSubtitle>
          </div>
        </div>
      </div>
    </a>
    <b-modal
      :id="`feature-card-modal-${cardId}`"
      :hide-footer="true"
      size="lg"
      header-bg-variant="dark"
      header-class="border-0"
      body-bg-variant="dark"
      centered
    >
      <template v-slot:modal-header="{ close }">
        <MCSubtitle>
          {{ title }}
        </MCSubtitle>
        <span class="float-right" @click="close()">
          <i class="fa fa-times" />
        </span>
      </template>
      <slot />
    </b-modal>
  </div>
</template>

<script>
import MCSubtitle from '~/components/mc/mc-subtitle'

export default {
  components: {
    MCSubtitle
  },
  props: {
    cardId: {
      type: String,
      required: true,
      default: ''
    },
    title: {
      type: String,
      required: true,
      default: ''
    },
    imageUrl: {
      type: String,
      required: true,
      default: ''
    }
  }
}
</script>

<style scoped>
a a:hover{
  text-decoration: none;
}

.feature-hover {
  transition: 250ms;
}

.feature-hover:hover {
  opacity: 0.8;
}

span {
  cursor: pointer;
}
</style>
