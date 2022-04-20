<template>
<div class="item m-1 mb-0">
  <div class="row">
    <div class="col-md-6 m-0 p-0">
        <b-button style="background:transparent; border:0; height: 170px; width: 100%; object-fit: cover"  @click="details(1)"><img src="../../../dist/static/images/large_66666643_2409023562674979_845509877525643264_n.jpg" class="img-responsive center-block" style="height: 100%; width: 100%; object-fit: cover"></b-button>
    </div>
    <div class="col-md-6 m-0 p-0">
        <br><h10 class="text-center">Text text text text text text text text text text text text text text text text text</h10>
    </div>
  </div>
  <div>
        <b-button style="background:transparent; border:0; color: black; text-align:left; font-size: 13px"><b>ЧТО ПОЧИТАТЬ В ЖАНРЕ ПРИКЛЮЧЕНИЯ, ПОГРУЖАЯСЬ В МИР ИСТОРИЙ</b></b-button>
        <br><h8 class="text-center p-3">24.03.2022</h8>
  </div>
</div>
</template>

<script>
import { loadScript } from 'vue-plugin-load-script'

loadScript('../../../dist/static/js/card.js')
export default {
  name: 'BlogCardInteresting',
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
