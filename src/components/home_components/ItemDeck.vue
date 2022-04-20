<template>
  <div class="m-5">
    <b-btn class="float-right" pill variant="outline-secondary" v-on:click="seeAll(product_category)">See all</b-btn>
    <h2>{{product_category}}</h2>
    <carousel
    :autoplay="false"
    :nav="true"
    :items=10
    :responsive = "{
        0:{items:1},576:{items:2},768:{items:2},1200:{items:4},1500:{items:5}
   }"
   :responsivebaseelement="body"
   >
        <div v-for="product in products" :key="product.Title">
          <item-card :item="product" :updateCart="updateCart"></item-card>
        </div>
      <!-- <template slot="prev" class="owl-prev"><span class="prev">prev</span></template>
      <template slot="next" class="owl-next"><span class="next">next</span></template> -->
    </carousel>
  </div>
  <!-- <div class="mt-5">
  <b-btn class="float-right" pill variant="outline-secondary" v-on:click="seeAll(product_category)">See all</b-btn>
  <h2>{{product_category}}</h2>
  <flickity  class="flickity" ref="flickity" :options="flickityOptions" style="">
    <div class="carousel-cell col-sm-3" v-for="product in products" :key="product.Title">
      <item-card :item="product" :updateCart="updateCart"></item-card>
    </div>
  </flickity>
  </div> -->
  <!-- <b-card class="mt-3 light" style="border: 0" :title="product_category">
    <b-card-body>
  <h4>{{products}}</h4>

      <b-card-group deck class="row">
          <div class="col-sm-5" v-for="product in products" :key="product.Title">
              <item-card :item="product" :updateCart="updateCart"></item-card>
          </div>
      </b-card-group>
    <b-btn class="float-right" pill variant="outline-secondary" v-on:click="seeAll(product_category)">Seen all</b-btn>
    </b-card-body>
    <div class="card-pagination">
        <div class="page-index" v-for="i in nbPages" :key="i"  @click="goto(i)" :class={active:currentPage(i)}></div>
    </div>
  </b-card> -->
</template>

<script>
import ItemCard from '@/components/common_components/ItemCard'
import Flickity from 'vue-flickity'
import carousel from 'vue-owl-carousel'
// import { loadScript } from 'vue-plugin-load-script'

// loadScript('../../../dist/static/js/jquery-2.2.4.min.js')
// loadScript('../../../dist/static/js/popper.js')
// loadScript('../../../dist/static/js/bootstrap.min.js')
// loadScript('../../../dist/static/js/owl.carousel.min.js')
// loadScript('../../../dist/static/js/main.js')

export default {
  name: 'ItemDeck',
  components: {
    'item-card': ItemCard,
    Flickity,
    carousel
  },
  props: ['products', 'product_category', 'updateCart'],
  methods: {
    seeAll (category) {
      this.$router.push('/categories/' + category)
    }
  },
  data () {
    return {
      flickityOptions: {
        initialIndex: 6,
        prevNextButtons: true,
        pageDots: true,
        wrapAround: true,
        freeScroll: true
        // any options from Flickity can be used
      }
    }
  }
}
</script>

<style scoped>

</style>
