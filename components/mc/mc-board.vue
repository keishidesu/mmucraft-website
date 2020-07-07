<template>
  <b-container fluid>
    <b-row align-h="center" class="mt-5">
      <b-col cols="12" md="8" class="mt-5 position-relative text-light">
        <b-card class="animated fadeInUp bg-dark shadow-lg">
          <slot />
        </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>
