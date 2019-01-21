<template>
  <div>
    <home-head></home-head>
    <home-swiper></home-swiper>
    <home-icons></home-icons>
    <home-recommend></home-recommend>
    <home-weekend></home-weekend>
  </div>
</template>

<script>
import HomeHead from './components/HomeHead'
import HomeSwiper from './components/HomeSwiper'
import HomeIcons from './components/HomeIcons'
import HomeRecommend from './components/Recommend'
import HomeWeekend from './components/Weekend'

export default {
  name: 'Home',
  components: { HomeHead, HomeSwiper, HomeIcons, HomeRecommend, HomeWeekend },
  data () {
    return {
    }
  }
}
</script>

<style></style>
