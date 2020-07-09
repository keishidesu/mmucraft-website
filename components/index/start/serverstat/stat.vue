<template>
  <b-row class="justify-content-center">
    <b-col cols="5" class="text-white text-center">
      {{ name }} server
    </b-col>
    <b-col cols="1" class="text-white">
      <i
        v-b-popover.hover.top="`${['Online', 'Offline', 'Unknown'][status]}${(status === 0) ? ` - ${version}` : ''}`"
        :class="{active: (status === 0), inactive: (status === 1), unknown: (status === 2)}"
        class="fa fa-circle"
      />
    </b-col>
    <b-col cols="5" class="text-white">
      <span v-if="status === 0">
        {{ currentPlayers }} / {{ maxPlayers }}
      </span>
      <span v-else>
        -
      </span>
    </b-col>
  </b-row>
</template>

<script>
export default {
  props: {
    name: {
      type: String,
      required: true,
      default: ''
    },
    maxPlayers: {
      type: Number,
      required: true,
      default: 0
    },
    currentPlayers: {
      type: Number,
      required: true,
      default: 0
    },
    version: {
      type: String,
      required: true,
      default: ''
    },
    status: {
      type: Number,
      required: true,
      default: 1
    }
  }
}
</script>

<style scoped>
/*icon color to show server is active or not*/
.active {
  color:rgb(124,252,0);
}

.inactive {
  color:rgb(139,0,0);
}

.unknown {
  color:rgb(189,152,50);
}
</style>
