<template>
  <div class="recommend">
    <div class="recommend_title">热销推荐</div>
    <ul>
      <li class="item border-bottom" v-for=" item of recommendList" :key="item.id">
          <img class="item_pic" :src="item.imgUrl" />
        <div class="item_desc">
          <p class="item_title">{{item.title}}</p>
          <p class="item_text">{{item.text}}</p>
          <button class="more_btn">查看更多</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props: {
    recommendList: Array
  }
  // data () {
  //   return {
  //     recommendList: [{
  //       id: '01',
  //       imgUrl: 'http://img1.qunarzz.com/sight/p0/1705/10/10e2be2a239cf3f2a3.img.jpg_200x200_f56735fb.jpg',
  //       title: '黄河梦幻水世界',
  //       text: '黄河梦幻水世界黄河梦幻水世界黄河梦幻'
  //     }, {
  //       id: '02',
  //       imgUrl: 'http://img1.qunarzz.com/sight/p0/1705/10/10e2be2a239cf3f2a3.img.jpg_200x200_f56735fb.jpg',
  //       title: '黄河梦幻水世界',
  //       text: '黄河梦幻水世界黄河梦幻水世界黄河梦幻'
  //     }, {
  //       id: '03',
  //       imgUrl: 'http://img1.qunarzz.com/sight/p0/1705/10/10e2be2a239cf3f2a3.img.jpg_200x200_f56735fb.jpg',
  //       title: '黄河梦幻水世界',
  //       text: '黄河梦幻水世界黄河梦幻水世界黄河梦幻'
  //     }, {
  //       id: '04',
  //       imgUrl: 'http://img1.qunarzz.com/sight/p0/1705/10/10e2be2a239cf3f2a3.img.jpg_200x200_f56735fb.jpg',
  //       title: '黄河梦幻水世界',
  //       text: '黄河梦幻水世界黄河梦幻水世界黄河梦幻'
  //     }
  //     ]
  //   }
  // }
}
</script>

<style lang="stylus" scoped>
@import '~style/mixins.styl'
.recommend_title
  height: 47px
  line-height: 47px
  background-color: #eee
  margin-top 5px
  text-indent 20px
.item
  height 120px
  display flex
  overflow hidden
.item_pic
  width  100px
  height 100px
  padding 10px
.item_desc
  flex 1
  padding 10px
  min-width 0
  .item_title
    margin-top 13px
    height 22px
    line-height 22px
    font-size 16px
    ellipsis()
  .item_text
    margin-top 7px
    height 17px
    color #ccc
    ellipsis()
  .more_btn
    margin-top 8px
    line-height 22px
    padding 0 4px
    border-radius 3px
    border 0
    color #ffffff
    background-color #f60

</style>
