<template>
  <div class="wrapper">
  <!--v-if 防止后台数据没传过来时，用空数组创建变成默认显示最后一张  -->
  <swiper :options="swiperOption" v-if="showSwiper">
    <swiper-slide v-for="item of swiperList" :key="item.id">
      <img class="swiper_img" :src="item.imgUrl">
    </swiper-slide>
    <div class="swiper-pagination"  slot="pagination"></div>
  </swiper>
  </div>
</template>
<script type="text/javascript">
export default {
  name: 'HomeSwiper',
  props: {
    swiperList: Array
  },
  data () {
    return {
      swiperOption: {
        loop: true,
        autoplay: 2000,
        pagination: '.swiper-pagination'
      }
      // swiperList: [{
      //   id: '01',
      //   imgUrl: 'http://img1.qunarzz.com/piao/fusion/1812/81/d2e6ecdcae6c3802.jpg_750x200_690c8f1c.jpg'
      // }, {
      //   id: '02',
      //   imgUrl: 'http://img1.qunarzz.com/piao/fusion/1811/7c/8e5c4ab8ee8b7402.jpg_750x200_dd7a38dd.jpg'
      // }, {
      //   id: '03',
      //   imgUrl: 'http://img1.qunarzz.com/piao/fusion/1811/a8/cb43c4ac6c215d02.jpg_750x200_83dee994.jpg'
      // }]
    }
  },
  computed: {
    showSwiper () {
      return this.swiperList.length
    }
  }
}
</script>
<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background-color: #fff
.wrapper
  overflow: hidden
  width: 100%
  height: 0
  padding-bottom: 26.7%
.swiper_img
  width: 100%
</style>
