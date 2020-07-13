<template>
  <div>
    <b-navbar toggleable="lg" type="dark" class="fixed-top bg-dark py-2">
      <b-navbar-brand href="/">
        MMUC
      </b-navbar-brand>
      <b-navbar-toggle target="nav-collapse" />
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item
            v-for="(item,i) in navitems"
            :key="`nav-item-${i}`"
            :href="`${item.destination}`"
            class="nav-item"
          >
            {{ item.navitem }}
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      navitems: [
        {
          navitem: 'Home',
          destination: '/'
        },
        {
          navitem: 'Rules',
          destination: '/rules'
        },
        {
          navitem: 'Commands',
          destination: '/commands'
        }
      ]
    }
  }
}
</script>
