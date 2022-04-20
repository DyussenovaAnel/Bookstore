<template>
  <div>
    <div id="blog_div_back">
      <img  id="blog_img_back" src="../../dist/static/images/large_66666643_2409023562674979_845509877525643264_n.jpg"/>
      <div id="blog_div_in">
        <p id="title_text_blog"><b>БЛОГ</b></p>
        <br>
        <p>ЧТО ПОЧИТАТЬ В ЖАНРЕ ПРИКЛЮЧЕНИЯ, ПОГРУЖАЯСЬ В МИР ИСТОРИЙ<br>
        ЛОАМТЛВАОМ ВАЛО МВА ВАЛИЬ ЩД ЫВЩДМЫЛМИЫА М ВАЛДВТАМОВАТМВЛОА<br>
        ВАВ АВЩМДАЬТОМИАВЛИТВЛОИВЛАО</p>
      </div>
    </div>
    <div class="container pt-3">
      <div class="row mt-3" id="blog_div_first_section">
        <div class="col-md-4">
          <p><b>Интересное</b></p>
          <div>
            <BlogCardInteresting></BlogCardInteresting>
          </div>
          <div>
            <BlogCardInteresting></BlogCardInteresting>
          </div>
        </div>
        <div class="col-md-5">
          <BlogCardBig></BlogCardBig>
        </div>
        <div class="col-md-3">
          <p><b>Новое</b></p>
          <div>
            <BlogCardNew></BlogCardNew>
          </div>
          <div>
            <BlogCardNew></BlogCardNew>
          </div>
          <div>
            <BlogCardNew></BlogCardNew>
          </div>
          <div>
            <BlogCardNew></BlogCardNew>
          </div>
        </div>
      </div>
      <div class="row mt-3">
        <div v-for="index in 10" :key="index" class="col-md-3">
          <BlogCardHome></BlogCardHome>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BlogCardHome from './blogcards/BlogCardHome'
import BlogCardInteresting from './blogcards/BlogCardInteresting'
import BlogCardBig from './blogcards/BlogCardBig'
import BlogCardNew from './blogcards/BlogCardNew'

export default {
  name: 'Blog',
  props: ['dataset'],
  data () {
    return {
      'collections': this.dataset
    }
  },
  components: {
    BlogCardHome,
    BlogCardInteresting,
    BlogCardBig,
    BlogCardNew
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
#blog_img_back{
  width: 100%;
  height: 90vh;
  object-fit: cover;
  -webkit-filter: brightness(30%);
  top: 0;
  left: 0;
  float:left;
}
#blog_div_back{
  position: relative;
}
#blog_div_in{
  position: absolute;
  color:white;
  text-align:center;
  /* padding-left: 25%;
  padding-right: 25%;
  padding-top: 10%; */
}
#title_text_blog{
  font-size: 80px;
  line-height: 1;
  padding-top: 13%;
}
#blog_div_first_section{
  padding-top: 5%;
}
</style>
