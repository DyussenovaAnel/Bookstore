<template>
  <div>
    <div id="category_div_back">
      <img  id="category_img_back" src="../../dist/static/images/category_2.jpg"/>
      <div id="category_div_in">
        <p id="title_text"><b>ЛУЧШИЕ КНИГИ В ЖАНРЕ ПРИКЛЮЧЕНИЯ</b></p>
        <br>
        <p>ЧТО ПОЧИТАТЬ В ЖАНРЕ ПРИКЛЮЧЕНИЯ, ПОГРУЖАЯСЬ В МИР ИСТОРИЙ<br>
        ЛОАМТЛВАОМ ВАЛО МВА ВАЛИЬ ЩД ЫВЩДМЫЛМИЫА М ВАЛДВТАМОВАТМВЛОА<br>
        ВАВ АВЩМДАЬТОМИАВЛИТВЛОИВЛАО</p>
      </div>
    </div>
    <div class="container pt-3">
      <div class="row mt-3">
        <p id="description_text">Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки Описание подборки </p>
        <div v-for="item in computedItems" :key="item.Title+item.Price" class="col-md-3">
          <item-card :item="item" :updateCart="updateCart"></item-card>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import ItemCard from '@/components/common_components/ItemCard'
export default {
  name: 'Categories',
  props: ['dataset', 'updateCart'],
  data () {
    return {
      'collections': this.dataset
    }
  },
  components: {
    'item-card': ItemCard
  },
  computed: {
    computedItems () {
      let productList = this.collections.filter((element) => {
        if (element.Genre === this.$route.params.type) {
          return element
        }
      })
      return productList
    }
  }
}
</script>

<style scoped>
#category_img_back{
  width: 100%;
  height: 90vh;
  object-fit: cover;
  -webkit-filter: brightness(30%);
  top: 0;
  left: 0;
  float:left;
}
#category_div_back{
  position: relative;
}
#category_div_in{
  position: absolute;
  color:white;
  text-align:center;
}
#title_text{
  font-size: 80px;
  line-height: 1;
  padding-top: 13%;
}
#description_text{
  padding: 10%;
}
</style>
