<template>
    <div>
      <div class="container">
        <div class="row mt-4">
          <ProductImages></ProductImages>
          <div class="col-sm-7">
            <!-- <h1>{{product.Title}}</h1> -->
            <h1 class="font-weight-bold">Жила за морем гагара</h1>
            <br>
            <div class="row mt-4">
              <div class="col-sm-7">
                <p>"Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione"</p>
              </div>
              <div  class="col-sm-5 text-right">
                <p><b>Author:</b> {{product.Author}}
                <br><b>Publisher:</b> {{product.Publisher}}
                <br><b>Genre:</b> {{product.Genre}}</p>
              </div>
            </div>
            <div class="row mt-4">
              <div class="col-sm-7">
                <div class="row mt-2">
                  <div class="col-md-4 text-center">
                    <b-button style="margin:0;padding:0;width:100%; height:100%; background:transparent; border:0" v-on:click="paper = true, digital = false, audio = false">
                      <img  class="d-block img-fluid w-100 p-3" src="../../dist/static/images/book.png"/>
                      <span style="color:black">Бумажная книга</span>
                    </b-button>
                  </div>
                  <div class="col-md-4 text-center">
                    <b-button style="margin:0;padding:0;width:100%; height:100%; background:transparent; border:0" v-on:click="paper = false, digital = true, audio = false">
                      <img class="d-block img-fluid w-100 p-3" src="../../dist/static/images/digital-book.png"/>
                      <span style="color:black">Электронная книга</span>
                    </b-button>
                  </div>
                  <div class="col-md-4 text-center">
                    <b-button style="margin:0;padding:0;width:100%; height:100%;background:transparent; border:0" v-on:click="paper = false, digital = false, audio = true">
                      <img class="d-block img-fluid w-100 p-3" src="../../dist/static/images/audio-book.png"/>
                      <span style="color:black">Аудио книга</span>
                    </b-button>
                  </div>
                </div>
              </div>
            </div>
            <div class="row mt-4">
              <div id="book_card_paper" v-show="paper">
                <BookPaper :product="product" :updateCart="updateCart"></BookPaper>
              </div>
              <div id="book_card_audio" v-show="audio">
                <BookAudio :product="product"></BookAudio>
              </div>
              <div id="book_card_audio" v-show="digital">
                <BookDigital :product="product"></BookDigital>
              </div>
            </div>
          </div>
        </div>
        <!-- section 2 -->
        <div>
          <br>
          <hr>
          <div class="row">
            <div class="col-sm-7 w-50">
              <div>
                <!-- <p><b>Рейтинг Книги</b></p> -->
                <!-- rating -->
                <!-- <div>
                  <StarRating></StarRating>
                </div> -->
                <!--audio-->
                <div>
                  <p><b>Прослушать отрывок “Жила за морем Гагара”</b></p>
                  <ListenAudio msg="Hello Vue in CodeSandbox!" />
                </div>
              </div>
              <div></div>
            </div>
            <!--  В подборках -->
            <div class="col-sm-5 w-50" style="border-left: 1px solid grey">
              <div>
                <p><b>В подборках</b></p>
                <div>
                  <div class="row">
                    <div class="col-md-5">
                      <img src="../../dist/static/images/category_adventure.jpg" style="width:100%; height:130px; border-radius :10px"/>
                    </div>
                    <div class="col-md-7">
                    <p style="font-size:15px">ТОП-250 ЛУЧШИХ КНИГ</p>
                    <p style="font-size:12px">
                    Книги, которые должен прочитать
                    каждый. Начиная от классики
                    заканчивая современной литературой.
                    Топ самых лучших книг.
                    Топ самых лучших книг Топ самых
                    лучших книг</p>
                    </div>
                  </div>
                  <div class="row mt-2">
                    <div class="col-md-5">
                      <img src="../../dist/static/images/category_2.jpg" style="width:100%; height:130px;  border-radius :10px"/>
                    </div>
                    <div class="col-md-7">
                    <p style="font-size:15px">ТОП-250 ЛУЧШИХ КНИГ</p>
                    <p style="font-size:12px">
                    Книги, которые должен прочитать
                    каждый. Начиная от классики
                    заканчивая современной литературой.
                    Топ самых лучших книг.
                    Топ самых лучших книг Топ самых
                    лучших книг</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <!-- section 3 -->
      <div>
        <BookCarousel></BookCarousel>
      </div >
      <!-- section 4 -->
      <!-- review section -->
      <div class="container">
        <div class="col-md-8">
          <AddReview></AddReview>
          <div v-for="index in 10" :key="index">
            <Review></Review>
          </div>
        </div>
      </div>
      <!-- section 5 -->
      <!-- <div>
        <item-deck :products="getDisplayProducts(categories[1])" :product_category="categories[1]" :updateCart="updateCart"></item-deck>
      </div> -->
    </div>
</template>

<script>
import Data from '../assets/book_list.json'
import carousel from 'vue-owl-carousel'
import StarRating from './StarRating'
import BookCarousel from './BookCarousel'
import ListenAudio from './ListenAudio.vue'
import AddReview from './AddReview.vue'
import Review from './Review.vue'
import ItemDeck from './home_components/ItemDeck'
import ProductImages from './ProductImages.vue'
import BookPaper from './book_info_cards/book_paper.vue'
import BookAudio from './book_info_cards/book_audio.vue'
import BookDigital from './book_info_cards/book_digital.vue'

export default {
  name: 'ProductDetails',
  props: ['updateCart'],
  components: {
    carousel,
    StarRating,
    BookCarousel,
    ListenAudio,
    AddReview,
    Review,
    'item-deck': ItemDeck,
    ProductImages,
    BookPaper,
    BookAudio,
    BookDigital
  },
  data () {
    return {
      collection: Data.collection,
      product: [],
      paper: true,
      audio: false,
      digital: false
    }
  },
  created () {
    // this.categories = this.getCategories()
    this.product = this.collection.find((item) => {
      return item.Title === this.$route.params.productID
    })
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
    seeAll (category) {
      this.$router.push('/categories/' + category)
    }
  }
}
</script>

<style scoped>
.btn_fill{
  background-color: grey;
  color:white;
}
.btn_trans{
  background: transparent;
  border: 1px solid grey;
  color: grey;
}
</style>
