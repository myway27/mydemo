<template>
  <div class="search">
    <input class="search_input" type="text" placeholder="输入城市名或拼音">
  </div>
</template>

<script>

export default {
  name: 'Search',
  components: {},
  data () {
    return {
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'
.search
  height 36px
  padding 5px
  background-color $bgColor
.search_input
  width 100%
  height 31px
  line-height 31px
  text-align center
  border-radius: 5px
  background: #fff
  color #666
  box-sizing border-box
  padding 0 5px
</style>
