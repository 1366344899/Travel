<template>
  <ul class="list">
    <li class="item" v-for="item of letters" :key="item" @click="handleClick" @touchstart="handleTouchStart"
    @touchmove="handleTouchMove"
    @touchEnd="handleTouchEnd"
    :ref="item"
    >{{item}}</li>
  </ul>
</template>
<script>
export default {
  data () {
    return {
      touchStatus: false,
      startY: 0
    }
  },
  props: {
    cities: Object
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
  updated () {
    this.startY = this.$refs['A'][0].offsetTop
  },
  methods: {
    handleClick (e) {
      this.$emit('change', e.target.innerHTML)
    },
    handleTouchStart () {
      this.touchStatus = true
    },
    handleTouchMove (e) {
      if (this.touchStatus) {
        const touchY = e.touches[0].clientY - 74
        const index = Math.floor((touchY - this.startY) / 20)
        if (index >= 0 && index < this.letters.length) {
          this.$emit('change', this.letters[index])
        }
      }
    },
    handleTouchEnd () {
      this.touchStatus = false
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '../../../styles/varible.styl'
.list
  display:flex
  flex-direction: column
  justify-content: center
  position:absolute
  right: 0
  bottom: 0
  width: .4rem
  top: 1.58rem
  .item
    line-height:.4rem
    text-align: center
</style>
