<template>
  <div class="m-1">
    <carousel
    :autoplay="false"
    :nav="true"
    :items=2
    :center="true"
    :vautoHeight="true"
    :loop="true"
   >
        <div>
          <img  style="height: 70vh; width:auto;" src="../../dist/static/images/book_gagara_1.jpg"/>
        </div>
        <div>
          <img style="height: 70vh; width:auto;" src="../../dist/static/images/book_gagara_2.jpg"/>
        </div>
        <div>
          <img style="height: 70vh; width:auto;" src="../../dist/static/images/book_gagara_3.jpg"/>
        </div>
      <!-- <template slot="prev" class="owl-prev"><span class="prev">prev</span></template>
      <template slot="next" class="owl-next"><span class="next">next</span></template> -->
    </carousel>
  </div>
</template>

<script>
import CategoryCard from './CategoryCard'
import Flickity from 'vue-flickity'
import carousel from 'vue-owl-carousel'

export default {
  name: 'BookCarousel',
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
