<template>
  <!-- <div class="container">
    <b-card img-src="https://picsum.photos/600/300?image=1073"
            img-alt="Image"
            img-top
            tag="article"
            style="max-width: 20rem;"
            class="m-2 text-center">
      <p>
        {{item.Title}}
      </p>
      <p>
        Author: {{item.Author}}
      </p>
      <div>
        <p>{{item.Price}}</p>
        <b-button variant="info" @click.prevent="updateCart(item)"><v-icon name="cart-plus" /> </b-button>
        <b-button variant="primary" @click="details(item.Title)"><v-icon name="list" /> </b-button>
      </div>
    </b-card>
  </div> -->
  <!-- <div id="app">
    <div class="card-row">
      <div class="card">
        <img class="card-image" src="https://placeimg.com/640/480/nature">
        <div class="card-footer">
          <p class="card-text">RECIPE</p>
          <h3 class="card-title">Title</h3>
          <p class="card-text">by
            <span class="card-author">Author</span>
          </p>
        </div>
      </div>
    </div>
  </div> -->
<!-- <div id="product-card">
      <div id="product-front">
        <div class="shadow"></div>
          <img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/245657/t-shirt.png" alt="" />
          <div class="image_overlay"></div>
          <div id="view_details">View details</div>
          <div class="stats">
            <div class="stats-container">
              <span class="product_price">$39</span>
              <span class="product_name">Adidas Originals</span>
              <p>Men's running shirt</p>
              <div class="product-options">
                <strong>SIZES</strong>
                <span>XS, S, M, L, XL, XXL</span>
                <strong>COLORS</strong>
                <div class="colors">
                  <div class="c-blue"><span></span></div>
                  <div class="c-red"><span></span></div>
                  <div class="c-white"><span></span></div>
                  <div class="c-green"><span></span></div>
                </div>
              </div>
            </div>
          </div>
      </div>
      <div id="product-back">
        <div class="shadow"></div>
          <div id="carousel">
              <ul>
                  <li><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/245657/t-shirt-large.png" alt="" /></li>
                  <li><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/245657/t-shirt-large2.png" alt="" /></li>
                  <li><img src="https://s3-us-west-2.amazonaws.com/s.cdpn.io/245657/t-shirt-large3.png" alt="" /></li>
              </ul>
              <div class="arrows-perspective">
                  <div class="carouselPrev">
                      <div class="y"></div>
                    <div class="x"></div>
                  </div>
                  <div class="carouselNext">
                      <div class="y"></div>
                    <div class="x"></div>
                  </div>
              </div>
          </div>
          <div id="flip-back">
            <div id="cy"></div>
              <div id="cx"></div>
          </div>
      </div>
  </div>
</div> -->

<!-- <div class="product-grid m-1">
    <div class="product-image">
        <a href="#" class="image">
            <img src="../../../dist/static/images/large_Жила_за_морем_Гагара.jpg">
        </a>
        <span class="product-discount-label">-23%</span>
        <ul class="product-links">
            <li><a href="#"><i class="fa fa-search"></i></a></li>
            <li><a href="#"><i class="fa fa-heart"></i></a></li>
            <li><a href="#"><i class="fa fa-random"></i></a></li>
        </ul>
        <a href="" class="add-to-cart">Add to Cart</a>
    </div>
    <div class="product-content">
        <h3 class="title"><a href="#">Women's Blouse Top</a></h3>
        <div class="price">$53.55 <span>$68.88</span></div>
    </div>
</div> -->
<div class="item m-1">
  <div>
    <b-button style="background:transparent; border:0; height: 100%; width: 100%; object-fit: contain" @click="details(item.Title)"><img src="../../../dist/static/images/large_Жила_за_морем_Гагара.jpg" class="img-responsive center-block" style="height: 100%; width: 100%; object-fit: contain"></b-button>
    <h10 class="text-center"><b-button style="background:transparent; border:0; color: black; text-align:left" @click="details(item.Title)">{{item.Title}}</b-button></h10>
    <br><h10 class="text-center ml-3">{{item.Author}}</h10>
    <!-- <h5 class="text">{{item.Price}} тг.</h5> -->
    <div class = "row ml-3">
        <h5>{{item.Price}} тг.</h5>
        <div class="ml-auto">
          <b-button style="background:transparent; border:1; width: 20%;" ><img  src="../../../dist/static/images/heart.png" style="height: 100%; width: 100%; object-fit: contain"></b-button>
          <b-button style="background:transparent; border:1; width: 20%" @click.prevent="updateCart(item)"><img src="../../../dist/static/images/shopping-cart.png"  style="height: 100%; width: 100%; object-fit: contain"></b-button>
        </div>
    </div>
  </div>
</div>

</template>

<script>
import { loadScript } from 'vue-plugin-load-script'

loadScript('../../../dist/static/js/card.js')
export default {
  name: 'ItemCard',
  props: ['item', 'updateCart'],
  methods: {
    details (title) {
      this.$router.push('/products/' + title)
    }
  }
}
</script>

<style scoped>
/* @import '../../../dist/static/css/card.css';
@import 'https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css';
.product-grid{
    font-family: 'Poppins', sans-serif;
    text-align: center;
}
.product-grid .product-image{
    overflow: hidden;
    position: relative;
    z-index: 1;
}
.product-grid .product-image a.image{display: block; }
.product-grid .product-image img{
    width: 100%;
    height: auto;
}
.product-grid .product-discount-label{
    color: #fff;
    background: #A5BA8D;
    font-size: 13px;
    font-weight: 600;
    line-height: 25px;
    padding: 0 20px;
    position: absolute;
    top: 10px;
    left: 0;
}
.product-grid .product-links{
    padding: 0;
    margin: 0;
    list-style: none;
    position: absolute;
    top: 10px;
    right: -50px;
    transition: all .5s ease 0s;
}
.product-grid:hover .product-links{ right: 10px; }
.product-grid .product-links li a{
    color: #333;
    background: transparent;
    font-size: 17px;
    line-height: 38px;
    width: 38px;
    height: 38px;
    border: 1px solid #333;
    border-bottom: none;
    display: block;
    transition: all 0.3s;
}
.product-grid .product-links li:last-child a{ border-bottom: 1px solid #333; }
.product-grid .product-links li a:hover{
    color: #fff;
    background: #333;
}
.product-grid .add-to-cart{
    background: #A5BA8D;
    color: #fff;
    font-size: 16px;
    text-transform: uppercase;
    letter-spacing: 2px;
    width: 100%;
    padding: 10px 26px;
    position: absolute;
    left: 0;
    bottom: -60px;
    transition: all 0.3s ease 0s;
}
.product-grid:hover .add-to-cart{ bottom: 0; }
.product-grid .add-to-cart:hover{ text-shadow: 4px 4px rgba(0,0,0,0.2); }
.product-grid .product-content{
    background: #fff;
    padding: 15px;
    box-shadow: 0 0 0 5px rgba(0,0,0,0.1) inset;
}
.product-grid .title{
    font-size: 16px;
    font-weight: 600;
    text-transform: capitalize;
    margin: 0 0 7px;
}
.product-grid .title a{
    color: #777;
    transition: all 0.3s ease 0s;
}
.product-grid .title a:hover{ color: #a5ba8d; }
.product-grid .price{
    color: #0d0d0d;
    font-size: 14px;
    font-weight: 600;
}
.product-grid .price span{
    color: #888;
    font-size: 13px;
    font-weight: 400;
    text-decoration: line-through;
}
@media screen and (max-width: 990px){
    .product-grid{ margin-bottom: 30px; }
} */
#slider-text{
  padding-top: 40px;
  display: block;
}
#slider-text .col-md-6{
  overflow: hidden;
}

#slider-text h2 {
  font-family: 'Josefin Sans', sans-serif;
  font-weight: 400;
  font-size: 30px;
  letter-spacing: 3px;
  margin: 30px auto;
  padding-left: 40px;
}
#slider-text h2::after{
  border-top: 2px solid #c7c7c7;
  content: "";
  position: absolute;
  bottom: 35px;
  width: 100%;
  }

#itemslider h4{
  font-family: 'Josefin Sans', sans-serif;
  font-weight: 400;
  font-size: 12px;
  margin: 10px auto 3px;
}
#itemslider h5{
  font-family: 'Josefin Sans', sans-serif;
  font-weight: bold;
  font-size: 12px;
  margin: 3px auto 2px;
}
#itemslider h6{
  font-family: 'Josefin Sans', sans-serif;
  font-weight: 300;;
  font-size: 10px;
  margin: 2px auto 5px;
}
.badge {
  background: #b20c0c;
  position: absolute;
  height: 40px;
  width: 40px;
  border-radius: 50%;
  line-height: 31px;
  font-family: 'Josefin Sans', sans-serif;
  font-weight: 300;
  font-size: 14px;
  border: 2px solid #FFF;
  box-shadow: 0 0 0 1px #b20c0c;
  top: 5px;
  right: 25%;
}
#slider-control img{
  padding-top: 60%;
  margin: 0 auto;
}
@media screen and (max-width: 992px){
#slider-control img {
  padding-top: 70px;
  margin: 0 auto;
}
}

.carousel-showmanymoveone .carousel-control {
  width: 4%;
  background-image: none;
}
.carousel-showmanymoveone .carousel-control.left {
  margin-left: 5px;
}
.carousel-showmanymoveone .carousel-control.right {
  margin-right: 5px;
}
.carousel-showmanymoveone .cloneditem-1,
.carousel-showmanymoveone .cloneditem-2,
.carousel-showmanymoveone .cloneditem-3,
.carousel-showmanymoveone .cloneditem-4,
.carousel-showmanymoveone .cloneditem-5 {
  display: none;
}
@media all and (min-width: 768px) {
  .carousel-showmanymoveone .carousel-inner > .active.left,
  .carousel-showmanymoveone .carousel-inner > .prev {
    left: -50%;
  }
  .carousel-showmanymoveone .carousel-inner > .active.right,
  .carousel-showmanymoveone .carousel-inner > .next {
    left: 50%;
  }
  .carousel-showmanymoveone .carousel-inner > .left,
  .carousel-showmanymoveone .carousel-inner > .prev.right,
  .carousel-showmanymoveone .carousel-inner > .active {
    left: 0;
  }
  .carousel-showmanymoveone .carousel-inner .cloneditem-1 {
    display: block;
  }
}
@media all and (min-width: 768px) and (transform-3d), all and (min-width: 768px) and (-webkit-transform-3d) {
  .carousel-showmanymoveone .carousel-inner > .item.active.right,
  .carousel-showmanymoveone .carousel-inner > .item.next {
    -webkit-transform: translate3d(50%, 0, 0);
    transform: translate3d(50%, 0, 0);
    left: 0;
  }
  .carousel-showmanymoveone .carousel-inner > .item.active.left,
  .carousel-showmanymoveone .carousel-inner > .item.prev {
    -webkit-transform: translate3d(-50%, 0, 0);
    transform: translate3d(-50%, 0, 0);
    left: 0;
  }
  .carousel-showmanymoveone .carousel-inner > .item.left,
  .carousel-showmanymoveone .carousel-inner > .item.prev.right,
  .carousel-showmanymoveone .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
@media all and (min-width: 992px) {
  .carousel-showmanymoveone .carousel-inner > .active.left,
  .carousel-showmanymoveone .carousel-inner > .prev {
    left: -16.666%;
  }
  .carousel-showmanymoveone .carousel-inner > .active.right,
  .carousel-showmanymoveone .carousel-inner > .next {
    left: 16.666%;
  }
  .carousel-showmanymoveone .carousel-inner > .left,
  .carousel-showmanymoveone .carousel-inner > .prev.right,
  .carousel-showmanymoveone .carousel-inner > .active {
    left: 0;
  }
  .carousel-showmanymoveone .carousel-inner .cloneditem-2,
  .carousel-showmanymoveone .carousel-inner .cloneditem-3,
  .carousel-showmanymoveone .carousel-inner .cloneditem-4,
  .carousel-showmanymoveone .carousel-inner .cloneditem-5,
  .carousel-showmanymoveone .carousel-inner .cloneditem-6  {
    display: block;
  }
}
@media all and (min-width: 992px) and (transform-3d), all and (min-width: 992px) and (-webkit-transform-3d) {
  .carousel-showmanymoveone .carousel-inner > .item.active.right,
  .carousel-showmanymoveone .carousel-inner > .item.next {
    -webkit-transform: translate3d(16.666%, 0, 0);
    transform: translate3d(16.666%, 0, 0);
    left: 0;
  }
  .carousel-showmanymoveone .carousel-inner > .item.active.left,
  .carousel-showmanymoveone .carousel-inner > .item.prev {
    -webkit-transform: translate3d(-16.666%, 0, 0);
    transform: translate3d(-16.666%, 0, 0);
    left: 0;
  }
  .carousel-showmanymoveone .carousel-inner > .item.left,
  .carousel-showmanymoveone .carousel-inner > .item.prev.right,
  .carousel-showmanymoveone .carousel-inner > .item.active {
    -webkit-transform: translate3d(0, 0, 0);
    transform: translate3d(0, 0, 0);
    left: 0;
  }
}
</style>
