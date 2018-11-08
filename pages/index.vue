<template>
  <section class="container">
    <div v-swiper:mySwiper="swiperOption">
    <div class="swiper-wrapper">
      <div class="swiper-slide" v-for="(banner, index) in banners" :key="index">
        <div>
          <img :src="banner">
          <h1>Tu titulo es {{ index }}</h1>
        </div>
      </div>
    </div>
    <div class="swiper-pagination"></div>
  </div>
  </section>
</template>

<script>
export default {
  data () {
      return {
        banners: [ 
          'https://via.placeholder.com/150', 
          'https://via.placeholder.com/150', 
          'https://via.placeholder.com/150', 
          'https://via.placeholder.com/150', 
          'https://via.placeholder.com/150', 
          'https://via.placeholder.com/150', 
          'https://via.placeholder.com/150', 
          'https://via.placeholder.com/150', 
          'https://via.placeholder.com/150', 
          'https://via.placeholder.com/150', 
          'https://via.placeholder.com/150' 
          ],
        swiperOption: {
          slidesPerView: 5,
          centeredSlides: true,
          spaceBetween: 50,
          pagination: {
            el: '.swiper-pagination',
            clickable: true
          }
          // some swiper options...
        }
      }
    },
    mounted() {
      console.log(
        'This is current swiper instance object', this.mySwiper, 
        'It will slideTo banners 3')
      this.mySwiper.slideTo(3, 1000, false)
    }
}
</script>

<style>

.container {
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
