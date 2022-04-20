<template>
  <b-navbar toggleable="md" type="light" variant="white">
    <div class="container">
      <b-navbar-toggle target="nav_collapse"></b-navbar-toggle>
      <b-navbar-brand href="#" @click.prevent="route_to('/')"><MainLogo /></b-navbar-brand>
      <b-collapse is-nav id="nav_collapse" >
        <b-navbar-nav class="ml-auto" right>
          <b-nav-item href="#" @click.prevent="route_to('/')">Главная</b-nav-item>
          <b-nav-item href="#" @click.prevent="route_to('/')">Контакты</b-nav-item>
          <b-nav-item href="#" @click.prevent="route_to('/')">Об Издательстве</b-nav-item>
          <b-nav-item href="#" @click.prevent="route_to('/')">Авторам</b-nav-item>

          <!-- <b-nav-item href="#" @click.prevent="route_to('/all-products')">All products</b-nav-item> -->
          <b-nav-item-dropdown text="Категории" >
            <b-dropdown-item href="#" v-for="category in categories" :key="category" @click.prevent="route_to('/categories/'+category)">{{category}}</b-dropdown-item>
          </b-nav-item-dropdown>
        </b-navbar-nav>
        <!-- Right aligned nav items -->
        <b-navbar-nav class="ml-auto">
          <b-button variant="primary" @click="checkout" right>
            Корзина <b-badge variant="light">${{purchase}}</b-badge>
          </b-button>
        </b-navbar-nav>
      </b-collapse>
    </div>
  </b-navbar>
</template>

<script>
import MainLogo from '../../assets/logo_rus.svg'

export default {
  name: 'Navbar',
  components: {
    MainLogo
  },
  props: ['categories', 'purchase'],
  methods: {
    checkout () {
      this.$router.push('/checkout')
    },
    route_to (path) {
      this.$router.push(path)
    }
  }
}
</script>

<style scoped>

</style>
