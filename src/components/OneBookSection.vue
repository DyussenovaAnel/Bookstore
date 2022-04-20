<template>
  <div class="container">
    <div id="bg" :blur="30">
        <div id="bg_black" class="row">
            <div id="text_bestseller" class="col-sm-6">
                <p>БЕСТСЕЛЛЕРЫ</p>
                <h2>Эгги Мортон, королева разгадок. Тело под роялем</h2>
                <br>
                <br>
                <br>
                <p>Автор: Эгги Мортон</p>
                <p>1902 год. Эгги Мортон живёт в небольшом городе на английском побережье. Предприимчивая, наделённая богатым воображением, но весьма застенчивая девочка, Эгги печалится после ухода из жизни её папы, и в её жизни мало что происходит... </p>
                <h1>2500 тг.</h1>
                <!-- <p>БЕСТСЕЛЛЕРЫ</p>
                <h2>{{item.Title}}</h2>
                <br>
                <br>
                <br>
                <p>Автор: {{item.Author}}</p>
                <p>1902 год. Эгги Мортон живёт в небольшом городе на английском побережье. Предприимчивая, наделённая богатым воображением, но весьма застенчивая девочка, Эгги печалится после ухода из жизни её папы, и в её жизни мало что происходит... </p>
                <h1>{{product.Price}} тг.</h1> -->
            </div>
            <div class="col-sm-6 p-5">
                <img id="img_bestseller" class="float-left" src="../../dist/static/images/2892144_detail.jpg">
            </div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'OneBookSection',
  props: ['dataset', 'updateCart'],
  data () {
    return {
      'collections': this.dataset
    }
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
div#bg {
    -webkit-background-size: cover;
    -moz-background-size: cover;
    -o-background-size: cover;
    background-size: cover;
    background-repeat: no-repeat;
    height: 90vh;
    background-image: url('../../dist/static/images/2892144_detail_bg.jpg');
    /* -webkit-filter: brightness(30%); */
}
#bg_black{
    height: 90vh;
    width: auto;
    background: rgba(0,0,0,0.7);
}
#img_bestseller{
    width: 60%;
    height: 90%;
}
#text_bestseller{
    color: white;
    padding: 7%;
    padding-left: 12%;
}

@media screen and (max-width: 900px) {
  #img_bestseller {
    display: none;
  }
}

</style>
