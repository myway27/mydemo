<template>
  <div class="icon">
    <swiper>
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <div class="icon_img" v-for="item of page" :key="item.id">
          <div class="img_pic">
            <img class="img" :src="item.imgUrl">
          </div>
          <p class="icon_text">{{item.iconTitle}}</p>
        </div>
      </swiper-slide>
    </swiper>
  </div>
</template>

<script>
export default {
  name: 'HomeIcons',
  data () {
    return {
      iconList: [{
        id: '01',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        iconTitle: '热门景点'
      }, {
        id: '02',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
        iconTitle: '一日游'
      }, {
        id: '03',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
        iconTitle: '动植物园'
      }, {
        id: '04',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
        iconTitle: '特价门票'
      }, {
        id: '05',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
        iconTitle: '滑雪季'
      }, {
        id: '06',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png',
        iconTitle: '泡温泉'
      }, {
        id: '07',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
        iconTitle: '全家游'
      }, {
        id: '08',
        imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/80/416c6ab3368d1f02.png',
        iconTitle: '全部玩乐'
      }
      //  {
      //   id: '09',
      //   imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/76/eb88861d78fb9902.png',
      //   iconTitle: '哈哈哈'
      // }
      ]
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>

<style lang="stylus" scoped>
/*.icon
  overflow: hidden
  height: 150px
  display: flex
  flex-flow: row wrap;
  align-content: flex-start;
  .icon_img
    height: 75px
    box-sizing: border-box
    flex: 0 0 25%
    padding-bottom: 25px
    .img_pic
      height: 100%
      margin-left: 22%
      margin-top: 5px
    .icon_text
      font-size: 12px
      text-align: center*/
  .icon
    overflow hidden
    height 0
    padding-bottom 50%
    margin-top: 5px
  .icon_img
    position relative
    overflow hidden
    float left
    width 25%
    height 0
    padding-bottom 25%
  .img_pic
    position absolute
    top 0
    left 0
    right 0
    bottom 22px
    box-sizing border-box
  .img
    display block
    margin 0 auto
    height 100%
  .icon_text
    position absolute
    left 0
    right 0
    bottom 0
    height 22px
    line-height 22px
    text-align center
</style>
