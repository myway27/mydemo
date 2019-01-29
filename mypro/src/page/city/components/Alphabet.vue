<template>
    <ul class="alp_list" >
      <li class="item" v-for="(item, key) of cities" :key="key">
        {{key}}
      </li>
      <!-- <li class="item">A</li> -->
    </ul>
</template>

<script>

export default {
  name: 'Alphabet',
  props: {
    cities: Object
  },
  data () {
    return {
    }
  }
}
</script>

<style lang="stylus" scoped>
@import '~style/varibles.styl'
.alp_list
  position absolute
  top 89px
  right 0
  bottom 0
  width 20px
  display flex
  flex-direction column
  justify-content center
  .item
    text-align center
    line-height 20px
    color $bgColor
</style>
