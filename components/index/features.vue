<template>
  <div class="bg-mmucraft">
    <b-container class="py-5">
      <MCTitle>
        Servers
      </MCTitle>
      <b-row class="justify-content-center">
        <b-col cols="11" lg="4">
          <feature-card-survival />
        </b-col>
        <b-col cols="11" lg="4">
          <feature-card-creative />
        </b-col>
        <b-col cols="11" lg="4">
          <feature-card-civil />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import MCTitle from '~/components/mc/mc-title'
import FeatureCardCivil from '~/components/index/features/feature-card-civil'
import FeatureCardCreative from '~/components/index/features/feature-card-creative'
import FeatureCardSurvival from '~/components/index/features/feature-card-survival'

export default {
  components: {
    MCTitle,
    FeatureCardCivil,
    FeatureCardCreative,
    FeatureCardSurvival
  }
}
</script>
