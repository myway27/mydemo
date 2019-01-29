<template>
  <div class="list" ref="wrapper">
    <div>
      <div class="space">
        <div class="title border-topbottom">当前城市</div>
        <div class="btn_list">
          <div class=" btn_wrapper">
            <div class="btn">北京</div>
          </div>
        </div>
      </div>
      <div class="space">
        <div class="title border-topbottom">热门城市</div>
        <div class="btn_list">
          <div class=" btn_wrapper" v-for= "item of hotCities" :key="item.id">
            <div class="btn">{{item.name}}</div>
          </div>
        </div>
      </div>
      <div class="space" v-for="(item, key) of cities" :key="key">
        <div class="title border-topbottom" >{{key}}</div>
        <div class="item_list">
          <div class="item border-bottom" v-for="keyItem of item" :key="keyItem.id">
            {{keyItem.name}}
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
  name: 'CityList',
  components: {BScroll},
  props: {
    cities: Object,
    hotCities: Array
  },
  data () {
    return {
    }
  },
  mounted () {
    this.scroll = new BScroll(this.$refs.wrapper)
  }
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'
.border-topbottom
  &:before
    border-color #cccccc
  &:after
    border-color #cccccc
.border-bottom
  &:before
    border-color #cccccc
.list
  position absolute
  top 89px
  right 0
  left 0
  bottom 0
  overflow hidden
.title
  line-height 32px
  padding-left 10px
  background-color #eee
  font-size 14px
  color #666
.btn_list
  padding: 5px 30px 5px 5px
  overflow hidden
  .btn_wrapper
    float left
    width 33.33%
    .btn
      margin 5px
      padding 5px 0
      text-align center
      border 1px solid #cccccc
      border-radius 3px
.item_list
  .item
    line-height 38px
    padding-left 10px
</style>
