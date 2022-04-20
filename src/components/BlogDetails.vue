<template>
  <div class="container pt-5">
      <div class="row">
        <div class="col-md-8" id="category_div_back">
            <div id="category_div_in" class="pb-2">
                <span>21 марта 2021</span><br>
                <span id="title_text"><b>Золотой ключ</b></span><br>
                <span>Авторы: Авторов А.А.  Авторов А.А.   Авторов А.А.   Авторов А.А.</span>
                <br>
            </div>
            <img  id="category_img_back" src="../../dist/static/images/large_66666643_2409023562674979_845509877525643264_n.jpg"/>
            <div class="pt-3" id="blog_text" style="padding-top: 10%">
                <div style="text-align:right; padding-left:40%">
                    <span><b><i>Сказочная история о мальчике, которому нравилось сумерничать под раскидистым старым деревом рядом со своей двоюродной бабушкой. Тем более, что она рассказывала ему о невероятных волшебных вещах.</i></b></span>
                </div>
                <div style="padding-top:10%">
                    Сказочная история о мальчике, которому нравилось сумерничать под раскидистым старым деревом рядом со своей двоюродной бабушкой. Тем более, что она рассказывала ему о невероятных волшебных вещах.Однажды бабушка поведала внуку, что тот, кто сможет добраться до подножия радуги, найдет там золотой ключ. И – о чудо! – вскоре именно этому мальчику удается добраться до нужного места. Но, обретя ключ, он не может успокоиться, ведь теперь ему предстоит отправиться на поиски замка, к которому он подошел. И вместе с ним на поиски тайны и раскрытия смыслов отправляются читатели.Совсем рядом, в доме торговца, который часто уезжал по делам, жила маленькая девочка. Мама ее давно умерла, так что следить за дочкой торговец поручил двум своим сестрам. А тех совсем не интересовала жизнь девочки. Настолько, что той все время приходилось ходить в крайне неопрятном виде. Да и обращались тетки с девочкой плохо.
                    С точки зрения домовых фей дом торговца был воплощением позора, и потому феи решили попросту выгнать девочку из дома. Хотя в ее неопрятности и не было ее вины.Она встретятся – мальчик и девочка – и вместе пойдут… к смерти и разлуке. Состарятся в пути и снова помолодеют. И снова состарятся.Если нужно пройти весь путь босиком – они пройдут. Если нудно испробовать смерть на вкус – они смогут пройти и этот уровень.Сложная, запутанная, полная приключений, неожиданных подарков и испытаний, история. Для ее автора, Джорджа Макдональда, она стала тем самым заветным потайным ящичком, куда он складывал все самое ценное, сокровенное, достойное для передачи и современникам, и детям следующих поколений. И вот – ящик передан. Но где же ключ?Очень красивая, оформленная в стиле борьбы теней, книга. Выбор техники не случаен, поскольку тени – важная часть этой истории.</div>
            </div>
        </div>
        <div class="col-md-4">
            <!-- <div v-for="item in computedItems" :key="item.Title+item.Price" class="col-md-3">
                <item-card :item="item" :updateCart="updateCart"></item-card>
            </div> -->
            <div class="" style="padding-top:20%">
                <span><b>Рекомендуем прочесть:</b></span>
                <div style="padding-top: 5%">
                    <span>«Лопуховое поле». Слово переводчику</span>
                    <span>21 марта 2021</span>
                </div>
                <div style="padding-top: 5%">
                    <span>История и миф. О новых сериях нон-фикшн</span>
                    <span>21 марта 2021</span>
                </div>
                <div style="padding-top: 5%">
                    <span>Каждому казалось, что он смотрит в зеркало</span>
                    <span>21 марта 2021</span>
                </div>
                <div style="padding-top: 5%">
                    <span>Зима тревоги нашей и гагар</span>
                    <span>21 марта 2021</span>
                </div>
            </div>
        </div>
      </div>
  </div>
</template>

<script>
import ItemCard from '@/components/common_components/ItemCard'
export default {
  name: 'BlogDetails',
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
      console.log(productList)
      return productList
    }
  }
}

// var items = computedItems()

</script>

<style scoped>
#category_img_back{
  width: 100%;
  height: 80vh;
  object-fit: cover;
  /* -webkit-filter: brightness(30%); */
  top: 0;
  left: 0;
  /* float:left; */
}
#category_div_back{
  /* position: relative; */
}
#category_div_in{
  /* position: absolute; */
  color:black;
  /* text-align:center; */
}
#title_text{
  font-size: 40px;
  line-height: 1;
  padding-top: 13%;
}
#description_text{
  padding: 10%;
}
#blog_text{
    /* align-content: left; */
}
</style>
