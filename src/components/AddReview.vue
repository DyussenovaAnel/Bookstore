<template>
  <div>
    <div class="row">
        ОТЗЫВЫ НА КНИГУ “Жила за морем гагара”
    </div>
    <div class="row">
        <StarRating></StarRating>
    </div>
    <div class="row">
        <div class="col-sm-2">
            <img src="../../dist/static/images/person1.jpg" style="width: 100px; height: 100px; border-radius:50%"/>
        </div>
        <div class="col-sm-8">
        <textarea placeholder="Оставить отзыв..." style="height: 100px"/>
        </div>
        <div class="col-sm-2 center">
            <b-button style="width: 50px; height: 50px; border-radius:50%"></b-button>
        </div>
    </div>
  </div>
</template>

<script>
import StarRating from './StarRating'
export default {
  name: 'AddReview',
  components: {
    StarRating
  }
}
</script>

<style scoped>
textarea{
    width:100%;
    border-radius:10px;
    border-color: #2B2A29;
}
</style>
