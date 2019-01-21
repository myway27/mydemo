<template>
  <div class="weekend">
    <div class="weekend_title">周末去哪儿</div>
    <ul>
      <li class="item border-bottom" v-for=" item of recommendList" :key="item.id">
        <div class="item_img">
          <img class="item_pic" :src="item.imgUrl" />
        </div>
        <div class="item_desc">
          <p class="item_title">{{item.title}}</p>
          <p class="item_text">{{item.text}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  data () {
    return {
      recommendList: [{
        id: '01',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1511/2b/5e0923cd15e06.jpg_r_640x214_b9c024c1.jpg',
        title: '细数舒适温泉',
        text: '有没有让你心动的温泉'
      }, {
        id: '02',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1511/2b/5e0923cd15e06.jpg_r_640x214_b9c024c1.jpg',
        title: '细数舒适温泉',
        text: '有没有让你心动的温泉'
      }, {
        id: '03',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1511/2b/5e0923cd15e06.jpg_r_640x214_b9c024c1.jpg',
        title: '细数舒适温泉',
        text: '有没有让你心动的温泉'
      }, {
        id: '04',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1511/2b/5e0923cd15e06.jpg_r_640x214_b9c024c1.jpg',
        title: '细数舒适温泉',
        text: '有没有让你心动的温泉'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~style/mixins.styl'
.weekend_title
  height: 47px
  line-height: 47px
  background-color: #eee
  text-indent 20px
.item_img
  overflow hidden
  height 0
  padding-bottom 33.9%
.item_pic
  width  100%
.item_desc
  padding 10px
  .item_title
    height 22px
    line-height 22px
    font-size 16px
    ellipsis()
  .item_text
    margin-top 7px
    height 17px
    color #ccc
    ellipsis()

</style>
