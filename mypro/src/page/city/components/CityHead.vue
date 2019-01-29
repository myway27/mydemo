<template>
  <div>
    <header>
      <router-link to="/">
        <div class="back iconfont">&#xe697;</div>
      </router-link>
      城市搜索
    </header>
  </div>
</template>

<script>

export default {
  name: 'CityHead',
  components: {},
  data () {
    return {
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'
header
  overflow hidden
  height $headerHeight
  line-height $headerHeight
  text-align center
  color #ffffff
  background-color $bgColor
  font-size 16px
  position relative
.back
  position absolute
  top 0
  left 0
  width: 40px
  color #ffffff
  text-align: center
  font-size: 25px

</style>
