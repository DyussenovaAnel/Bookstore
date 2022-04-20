<template>
<div class="item m-1">
  <div>
    <br>
    <div class="row mt-4">
        <div class="col-sm-8">
        <h3>Цена:<b>{{product.Price}} тг.</b></h3>
        </div>
        <!-- <div  class="col-sm-4 row" style="border:1px solid black;border-radius: 20px"> -->
        <div class="col-sm-4">
        <div class="row">
            <b-button class="col-sm-4">+</b-button>
            <div class="col-sm-4 text-center" style="border:1px solid black; text-align: center">
            <span>1</span>
            </div>
            <b-button class="col-sm-4">-</b-button>
        </div>
        </div>
    </div>
    <br>
    <p>
        <b>Бумажная книга:</b> “Аманат өмір немесе Тәңірі алдында теңбіз”<br>
        <b>Формат (Ш х В):</b> 220 х 290<br>
        <b>Переплет:</b> Твердый переплет<br>
        <b>Бумага:</b> Мелованная<br>
    </p>
    <div class="row">
        <b-btn class="col-sm-5 btn_fill m-1" @click.prevent="updateCart(product)">В корзину</b-btn>
        <b-btn class="col-sm-5 btn_trans m-1" @click.prevent="updateCart(product)">Вишлист</b-btn>
    </div>
    </div>
</div>

</template>

<script>
export default {
  name: 'BookPaper',
  props: ['product', 'updateCart'],
  methods: {
    details (title) {
      this.$router.push('/products/' + title)
    }
  }
}
</script>

<style scoped>

</style>
