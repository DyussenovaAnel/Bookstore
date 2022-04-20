<template>
  <div class="m-5">
    <h4>БЛОГ</h4>
    <a :href="'#/blog'" style="text-align: right;">Показать больше</a>
    <carousel
    :autoplay="false"
    :nav="true"
    :items=5
    :responsive = "{
        0:{items:1},576:{items:2},768:{items:2},1200:{items:4},1500:{items:5}
   }"
   :responsivebaseelement="body"
   >
        <div v-for="index in 6" :key="index">
            <BlogCardHome></BlogCardHome>
          <!-- <CategoryCard :item="category"></CategoryCard> -->
        </div>
    </carousel>
  </div>
</template>

<script>
import CategoryCard from './CategoryCard'
import Flickity from 'vue-flickity'
import carousel from 'vue-owl-carousel'
import BlogCardHome from './blogcards/BlogCardHome'

export default {
  name: 'BlogDeck',
  components: {
    CategoryCard,
    Flickity,
    carousel,
    BlogCardHome
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
