<template>
  <div class="mt-1">
    <b-carousel id="my-carousel"
                style="text-shadow: 1px 1px 2px #333;"
                controls
                indicators
                background="#FFFFF"
                :interval="4000"
                img-width="1024"
                img-height="480"
                v-model="slide"
                @sliding-start="onSlideStart"
                @sliding-end="onSlideEnd"
    >
    <b-carousel-slide>
        <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="../../../dist/static/images/Безымянный-2__Восстановлен__Монтажная_область_1_ec6f18833d4fe926fe57994053c3b6cf.png"
            alt="слот изображения"
          >
        </template>
      </b-carousel-slide>
      <b-carousel-slide>
        <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="../../../dist/static/images/Совместные_закупки.jpg"
            alt="слот изображения"
          >
        </template>
      </b-carousel-slide>
      <b-carousel-slide>
        <template #img>
          <img
            class="d-block img-fluid w-100"
            width="1024"
            height="480"
            src="../../../dist/static/images/Совместные_закупки.jpg"
            alt="слот изображения"
          >
        </template>
      </b-carousel-slide>
    </b-carousel>
  </div>
</template>

<script>
export default {
  data () {
    return {
      slide: 0,
      sliding: null
    }
  },
  methods: {
    onSlideStart (slide) {
      this.sliding = true
    },
    onSlideEnd (slide) {
      this.sliding = false
    }
  }
}
</script>

<style scoped>
  /* #my-carousel {
    margin-top: auto;
    height: 50%;
  }
  .item {
    position: absolute;
    top: 0;
    left: 0;
    min-height: 50%;
} */
</style>
