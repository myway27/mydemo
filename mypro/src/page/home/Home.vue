<template>
  <div>
    <home-head></home-head>
    <home-swiper></home-swiper>
    <p>aaa</p>
  </div>
</template>

<script>
import HomeHead from './components/HomeHead'
import HomeSwiper from './components/HomeSwiper'
export default {
  name: 'Home',
  components: { HomeHead, HomeSwiper },
  data () {
    return {
    }
  }
}
</script>

<style></style>
