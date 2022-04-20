<template>
  <div class="m-5">
    <!-- <carousel
    :autoplay="true"
    :nav="true"
    :items=5
    :loop="true"
    :responsive = "{
        0:{items:1},576:{items:2},768:{items:2},1200:{items:4},1500:{items:5}
   }"
   :responsivebaseelement="body"
   > -->
   <div class="row" style="text-align:center">
      <div class="col-md-2 ml-3 mr-3" v-for="index in 5" :key="index">
        <CategoryCard :item="categories[index]"></CategoryCard>
      </div>
   </div>
      <!-- <template slot="prev" class="owl-prev"><span class="prev">prev</span></template>
      <template slot="next" class="owl-next"><span class="next">next</span></template> -->
    <!-- </carousel> -->
  </div>
</template>

<script>
import CategoryCard from './CategoryCard'
import Flickity from 'vue-flickity'
import carousel from 'vue-owl-carousel'

export default {
  name: 'CategoriesDeck',
  components: {
    CategoryCard,
    Flickity,
    carousel
  },
  props: ['categories'],
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
      }
    }
  }
}
</script>

<style scoped>

</style>
