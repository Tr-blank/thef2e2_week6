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
          .swiper-pagination(slot="pagination")
        main
          .room-item
            img(src="")
          .room-item
            img(src="")
          .room-item
            img(src="")
          .room-item
            img(src="")
          .room-item
            img(src="")
          .room-item
            img(src="")

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

</style>
