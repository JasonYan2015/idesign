<template>
  <div class="hello">
    <swiper id="mySwiper" :options="swiperOption" ref="mySwiper" @someSwiperEvent="callback">
      <!-- slides -->
      <swiper-slide><img src="../assets/logo.png"> 1</swiper-slide>
      <swiper-slide><img src="../assets/logo.png"> 2</swiper-slide>
      <swiper-slide><img src="../assets/logo.png"> 3</swiper-slide>
      <swiper-slide><img src="../assets/logo.png"> 4</swiper-slide>
      <swiper-slide><img src="../assets/logo.png"> 5</swiper-slide>
      <swiper-slide><img src="../assets/logo.png"> 6</swiper-slide>
      <swiper-slide><img src="../assets/logo.png"> 7</swiper-slide>
      <!-- Optional controls -->
      <div class="swiper-scrollbar"   slot="scrollbar"></div>
    </swiper>
  </div>
</template>

<script>
import { swiper, swiperSlide } from 'vue-awesome-swiper'
import 'swiper/dist/css/swiper.css'

export default {
  name: 'HelloWorld',
  components: {
    swiper,
    swiperSlide
  },
  data () {
    return {
      msg: 'this is the hello world component',
      swiperOption: {
        scrollbar: {
          el: '.mySwiper'
        }
      }
    }
  },
  computed: {
      swiper() {
        return this.$refs.mySwiper.swiper
      }
    },
    mounted() {
      // current swiper instance
      // 然后你就可以使用当前上下文内的swiper对象去做你想做的事了
      console.log('this is current swiper instance object', this.swiper)
      this.swiper.slideTo(1, 1000, false)
    }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1, h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
.swiper-slide {
  width: 250px;
}
</style>
