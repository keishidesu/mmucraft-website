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
      <b-list-group flush>
        <b-list-group-item v-for="(feature, i) in features" :key="`civil-modal-feature-${i}`">
          <div class="card shadow-lg border-0 border-round">
            <img class="img-fluid card-img" :src="feature.imageUrl">
            <div class="card-img-overlay d-flex">
              <div class="my-auto p-md-3">
                <MCSubtitle class="card-title d-none d-md-block" :text-shadow="true">
                  {{ feature.header }}
                </MCSubtitle>
                <ul class="list-dark-overlay pr-3 py-3 d-none d-md-block">
                  <li v-for="(desc, j) in feature.desc" :key="`feature-desc-${i}-${j}`">
                    {{ desc }}
                  </li>
                </ul>
              </div>
            </div>
          </div>
          <h4 class="d-md-none mt-3">
            {{ feature.header }}
          </h4>
          <ul class="d-md-none">
            <li v-for="(desc, j) in feature.desc" :key="`feature-desc-${i}-${j}`">
              {{ desc }}
            </li>
          </ul>
        </b-list-group-item>
      </b-list-group>
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
    },
    features: {
      type: Array,
      required: true,
      default: () => []
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

.list-group-item {
  background-color: rgba(0, 0, 0, 0) !important;
}

.list-dark-overlay {
  background-color: rgba(0, 0, 0, .45);
  border-radius: 0.5rem;
}
</style>
