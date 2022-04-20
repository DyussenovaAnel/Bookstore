<template>
    <div class="col-sm-5">
        <img id="big_image" src="../../dist/static/images/large_Жила_за_морем_Гагара.jpg"/>
        <carousel
            :autoplay="false"
            :nav="true"
            :items=4
            :loop="true"
        >
            <div v-for="index in 5" :key="index">
                <button :id="'small_btn_'+index" @click="changeImg()">
                    <img :id="'small_image_'+index" class="d-block img-fluid w-100" src="../../dist/static/images/large_3D_ремарк.png"/>
                </button>
            </div>
        <!-- <template slot="prev" class="owl-prev"><span class="prev">prev</span></template>
        <template slot="next" class="owl-next"><span class="next">next</span></template> -->
        </carousel>
    </div>
</template>

<script>
import carousel from 'vue-owl-carousel'

export default {
  name: 'ProductImages',
  components: {
    carousel
  },
  methods: {
    changeImg: function () {
    //   var imags = document.getElementById(imga.id)
      console.log(this.$id)
    }
  }
}
</script>

<style scoped>
button{
    border:0;
    background: transparent;
}
textarea{
    width:100%;
    border-radius:10px;
    border-color: #2B2A29;
}
#review_div{
    border: 1px solid #2B2A29;
    border-radius:10px;
}
</style>
