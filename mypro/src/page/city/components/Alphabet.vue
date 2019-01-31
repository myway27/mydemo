<template>
    <ul class="alp_list" >
      <!--没有computed之前循环如下
        v-for="(item, key) of cities"
        :key="key"   -->
      <li class="item"
        v-for="item of letters"
        :key="item"
        :ref="item"
        @touchstart="handleTouchStart"
        @touchmove="handleTouchMove"
        @touchend="handleTouchEnd"
        @click="handleLetter"
      >
        {{item}}
      </li>
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
      touchStatus: false,
      startY: 0,
      timer: null
    }
  },
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  computed: {
    letters () {
      const letters = []
      for (let i in this.cities) {
        letters.push(i)
      }
      return letters
    }
  },
  methods: {
    handleLetter (e) {
      // console.log(e.target.innerText)
      // 子传父
      this.$emit('change', e.target.innerText)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      // if (this.touchStatus) {
      //   // 这样每次都要计算A距header的距离，优化如上在updated周期写
      //   // let startY = this.$refs['A'][0].offsetTop
      //   let touchY = e.touches[0].clientY - 89
      //   let num = Math.floor((touchY - this.startY) / 20)
      //   if (num >= 0 && num < this.letters.length) {
      //     this.$emit('change', this.letters[num])
      //   }
      // }
      if (this.touchStatus) {
        // 函数节流，提升性能，防着touchmove频率太快
        if (this.timer) {
          clearTimeout(this.timer)
        }
        this.timer = setTimeout(() => {
          let touchY = e.touches[0].clientY - 89
          let num = Math.floor((touchY - this.startY) / 20)
          if (num >= 0 && num < this.letters.length) {
            this.$emit('change', this.letters[num])
          }
        }, 16)
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
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
