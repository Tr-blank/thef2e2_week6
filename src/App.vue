<template lang="pug">
  .app
    swiper(:options="swiperOption")
      swiper-slide.index-bg(
        v-for="(slide, index) in swiperSlides"
        :key="index"
        :style="`background-image: url(${slide});`"
      )
    .app__container
      .app__content
        header
          img.logo(src="./assets/images/logo.svg")
          h1 好室旅店。HOUSE HOTEL
          address
            a.address__item(href="https://goo.gl/maps/UURBnfgJKHEXsYyGA") 花蓮縣花蓮市國聯一路1號
            a.address__item(href="tel:+88638321155") 038321155
            a.address__item(href="mailto:house@hotel.com") HOUSE@HOTEL.COM
          .swiper-pagination(slot="pagination")
        main.room
          .room__item
            img(src="./assets/images/index_room-item01.jpeg")
          .room__item
            img(src="./assets/images/index_room-item02.jpeg")
          .room__item
            img(src="./assets/images/index_room-item03.jpeg")
          .room__item
            img(src="./assets/images/index_room-item04.jpeg")
          .room__item
            img(src="./assets/images/index_room-item05.jpeg")
          .room__item
            img(src="./assets/images/index_room-item06.jpeg")

</template>

<script>
import { swiper, swiperSlide } from 'vue-awesome-swiper'

import indexBg01 from './assets/images/index_bg01.jpeg'
import indexBg02 from './assets/images/index_bg02.jpeg'
import indexBg03 from './assets/images/index_bg03.jpeg'
import indexBg04 from './assets/images/index_bg04.jpeg'

import './assets/style/normalize.css'
import './assets/style/reset.css'
import 'swiper/dist/css/swiper.css'

export default {
  name: 'App',
  components: {
    swiper,
    swiperSlide
  },
  data () {
    return {
      swiperOption: {
        slidesPerView: 1,
        effect: 'fade',
        loop: true,
        pagination: {
          el: '.swiper-pagination',
          bulletClass: 'swiper-pagination__bullet',
          bulletActiveClass: 'swiper-pagination__bullet--active',
          clickable: true
        }
      },
      swiperSlides: [
        indexBg01,
        indexBg02,
        indexBg03,
        indexBg04
      ]
    }
  },
  created () {

  },
  mounted () {
  },
  computed: {

  },
  methods: {
  }
}
</script>

<style lang="stylus">
.swiper-pagination__bullet
  width: 12px;
  height: 12px;
  border: 1px solid #fff
  border-radius: 12px;
  margin: 20px 10px;
  display: inline-block;
  &--active
    background: #fff;

</style>

<style lang="stylus" scoped>
.index-bg
  height: 100vh;
  background-size: cover;
  background-position: center center;
.app
  &__container
    position: absolute;
    top: 0;
    left: 0;
    background-color: rgba(0,0,0,.6);
    z-index: 10;
    width: 100%;
    height: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
  &__content
    max-width: 1024px
    display: flex;
    align-items: center;
header
  width: 20%;
  padding-right: 10%;
  color: #fff;
  font-size: 12px;
h1
  line-height: 18px;
  text-align: left;
  margin-top: 185.22px;
  font-size: 12px;
.address__item
  display: block;
.room
  display: flex;
  flex-wrap: wrap;
  &__item
    width 33.33%

</style>
