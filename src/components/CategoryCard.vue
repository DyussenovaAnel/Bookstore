<template>
<div class="item m-1" style="margin:20px;">
  <div id="category_card_div">
    <img id="category_crd_img" src="../../dist/static/images/category_4.jpg"/>
    <b-button id="bg_button" v-on:click="seeAll(item)">
    <!-- <img id="category_crd_img" src="../../dist/static/images/category_4.jpg"/> -->

      <div id="bg_div">
          <p><b>{{item}}</b><br>
          Психология очень интересная наука о поведении человека. Что подталкивает человека соверщать какие либо поступки. Разобраться в сложном поведении человека</p>
      </div>
    </b-button>

  </div>
</div>
</template>

<script>
export default {
  name: 'CategoryCard',
  props: ['item'],
  methods: {
    seeAll (category) {
      this.$router.push('/categories/' + category)
    }
  }
}
</script>

<style scoped>
#category_card_div  {
    height: 30vh;
    width: 35vh;
    line-height: 0.8em;
    /* margin:20px; */
    /* position: relative; */
}
#bg_button{
  /* position: absolute; */
  /* float:left; */
  position: relative;
  background: transparent;
  border:0;
}
#category_crd_img{
  -webkit-filter: brightness(50%);
  object-fit: cover;
  width: 100%;
  height: 100%;
  border-radius: 5px;
  position: absolute;
  /* float:left; */
  /* position: relative; */
}
#bg_div{
  /* position: absolute; */
  color: white;
  padding-top: 40%;
  padding-right: 5%;
  /* padding-left: 5%; */
  padding-bottom: 5%;
  line-height: 1;
  font-size: 15px;
  text-align: left;
}

</style>
