<template>
<div class="item m-1 mb-1">
  <div>
    <b-button style="background:transparent; border:0; height: 200px; width: 100%; object-fit: cover"  @click="details(1)"><img src="../../../dist/static/images/large_66666643_2409023562674979_845509877525643264_n.jpg" class="img-responsive center-block" style="height: 100%; width: 100%; object-fit: cover"></b-button>
    <h10 class="text-center"><b-button style="background:transparent; border:0; color: black; text-align:left"   @click="details(1)"><b>Blog text</b></b-button></h10>
    <br><span class="pl-2">24/03/2022</span>
    <div class="pl-2 pr-2 pt-0 mt-0"><br><h10 class="text-center ">Text text text text text text text text text text text text text text text text text</h10></div>
  </div>
</div>
</template>

<script>
import { loadScript } from 'vue-plugin-load-script'

loadScript('../../../dist/static/js/card.js')
export default {
  name: 'BlogCardHome',
  // props: ['item', 'updateCart'],
  methods: {
    details (title) {
      this.$router.push('/blog/' + title)
    }
  }
}
</script>

<style scoped>
</style>
