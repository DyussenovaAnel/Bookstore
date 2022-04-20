<template>
  <div>
    <div class="row p-4 m-1 mt-3" id="review_div">
        <div class="col-sm-2">
            <img src="../../dist/static/images/person1.jpg" style="width: 100px; height: 100px; border-radius:50%"/>
        </div>
        <div class="col-sm-9">
            <div style="justify-content: space-between;display: flex;">
                <span style="float:left"><b>Имя фамилия</b></span>
                <span style="float:right; font-size:12px">24 вапр 2021</span>
            </div>
            <span>
                ОтзывОтзыв Отзыв Отзыв ОтзывОтзыв Отзыв Отзыв Отзыв  мОтзыв ОтзывОтзыв Отзыв отзыв отзыв отзыв отзыв отзывотзыв отзыв отзыв  мотзыв отзыв м м м м м отзывотзывм  отзыв
            </span>
            <br>
            <span style="float:right; font-size:15px">7,8/10</span>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Review'
}
</script>

<style scoped>
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
