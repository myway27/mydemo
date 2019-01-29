<template>
<div>
  <header>
      <div class="header_box back iconfont">&#xe697;</div>
      <div class="header_box input">
          <span class="l search_icon iconfont">&#xe617;</span>
          <input class="search_val" type="text" placeholder="搜索:目的地/酒店/景点/航班号">
      </div>
      <router-link to="/city">
        <div class="header_box city">
          {{this.city}}<span class="iconfont">&#xe6aa;</span>
        </div>
      </router-link>
  </header>
</div>
</template>

<script>
export default {
  name: 'HomeHeader',
  props: {
    city: String
  },
  data () {
    return {
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '~style/varibles.styl'
header
  line-height: $headerHeight
  background-color: $bgColor
  display: flex
.header_box
  display: inline-block
.back
  width: 40px
  text-align: center
  font-size: 25px
.input
  display: flex
  flex: 1
  height: 30px
  line-height: 30px
  margin-top: 7px
  margin-right: 5px
  border-radius: 5px
  background: #fff
.search_icon
  width: 30px
  font-size: 20px
  text-align: center
.search_val
  flex: 1
  font-size: 15px
.city
  width: 50px
  color: #fff

</style>
