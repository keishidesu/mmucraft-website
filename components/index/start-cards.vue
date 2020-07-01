<template>
  <div>
    <b-row class="justify-content-center">
      <b-col
        v-for="(card,i) in cards"
        :key="`card-${i}`"
        cols="12"
        lg="3"
      >
        <b-card class="info-card bg-none text-center mt-3 h-100 border-0">
          <b-img :src="`/getstart/${card.image}.png`" />
          <b-card-title>
            {{ card.title }}
          </b-card-title>
          <b-card-text>
            {{ card.desc }}
          </b-card-text>
        </b-card>
      </b-col>
    </b-row>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      cards: [
        {
          image: 'pickaxe',
          title: 'Register',
          desc: 'For everyone!',
          destination: '/register'
        },
        {
          image: 'netherstar',
          title: 'Login',
          desc: 'View your minecraft profile and achievements',
          destination: '/login'
        },
        {
          image: 'discord',
          title: 'Discord Us',
          desc: 'Join our community in our discord server',
          destination: ''
        }
      ]
    }
  }
}
</script>

<style>
  .info-card:after {
    background: none repeat scroll 0 0 transparent;
    bottom: 0;
    content: "";
    height: 2px;
    left: 50%;
    position: absolute;
    background: #fff;
    transition: width 0.3s ease 0s, left 0.3s ease 0s;
    width: 0;
  }

  .info-card:hover:after {
    width: 100%;
    left: 0;
  }
</style>
