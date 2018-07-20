<template>
  <div class="banner">
    <swiper :options="swiperOption">
        <swiper-slide v-for="slide in swiperSlides" :key="slide.id">
          <!-- I'm Slide {{ slide }} -->
          <img :src="slide">
        </swiper-slide>
        <p class="swiper-pagination" slot="pagination"></p>
    </swiper>
  </div>
</template>
<script>
import 'swiper/dist/css/swiper.css'
import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
  name: 'banner',
  data () {
    return {
      swiperOption: {　　　　　
        autoplay:true,//自动切换
        pagination: {
          el: '.swiper-pagination'//分页器
        }
      },
      swiperSlides: ['/static/img/product/main-1.jpg','/static/img/product/main-2.jpg','/static/img/product/main-3.jpg','/static/img/product/main-4.jpg']
    }
  },
  components: {
    swiper,
    swiperSlide
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.banner img {
  width: 100%;
}
</style>
