<template>
  <div class="container" style="m-0 p-0">
    <div class="left">
      <carousel></carousel>
    </div>
    <div v-for="index in 2" :key="index">
      <item-deck :products="getDisplayProducts(categories[index])" :product_category="categories[index]" :updateCart="updateCart"></item-deck>
    </div>
    <div>
      <OneBookSection></OneBookSection>
    </div>
    <div>
      <CategoriesDeck :categories="categories"></CategoriesDeck>
    </div>
    <div>
      <item-deck :products="getDisplayProducts(categories[3])" :product_category="categories[3]" :updateCart="updateCart"></item-deck>
    </div>
    <div>
      <BookCarousel></BookCarousel>
    </div>
    <div>
      <item-deck :products="getDisplayProducts(categories[4])" :product_category="categories[4]" :updateCart="updateCart"></item-deck>
    </div>
    <div>
      <BlogDeck :categories="categories"></BlogDeck>
    </div>
    <!-- <div>
      <BlogCardHome></BlogCardHome>
    </div> -->
    <!-- <div v-for="index in range(4,10)" :key="index">
      <item-deck :products="getDisplayProducts(categories[index])" :product_category="categories[index]" :updateCart="updateCart"></item-deck>
    </div> -->
    <!-- <div v-for="(category) in categories" :key="category">
      <item-deck  :products="getDisplayProducts(category)" :product_category="category" :updateCart="updateCart"></item-deck>
    </div> -->
  </div>
</template>

<script>
import Carousel from './home_components/Carousel'
import ItemCard from './common_components/ItemCard'
import ItemDeck from './home_components/ItemDeck'
import OneBookSection from './OneBookSection'
import CategoriesDeck from './CategoriesDeck'
import CategoryCard from './CategoryCard'
import BookCarousel from './BookCarousel'
import BlogDeck from './BlogDeck'

export default {
  name: 'Home',
  props: ['dataset', 'updateCart'],
  data () {
    return {
      'collections': this.dataset,
      'categories': []
    }
  },
  components: {
    'carousel': Carousel,
    'item-card': ItemCard,
    'item-deck': ItemDeck,
    OneBookSection,
    CategoriesDeck,
    CategoryCard,
    BookCarousel,
    BlogDeck
  },
  created () {
    this.categories = this.getCategories()
  },
  methods: {
    getCategories: function () {
      let listedCategories = []
      this.collections.filter((item) => {
        if (!listedCategories.includes(item.Genre)) {
          listedCategories.push(item.Genre)
        }
      })
      return listedCategories
    },
    getDisplayProducts (category) {
      let productList = this.collections.filter((element) => {
        if (element.Genre === category) {
          return element
        }
      })
      return productList.slice(0, 10)
    },
    range: function (start, end) {
      return Array(end - start + 1).fill().map((_, idx) => start + idx)
    }
  }
}

</script>

<style scoped>
.container {
  font-family: 'Calibri';
  width:100%;
  max-width:none;
  padding:0;
  }
</style>
