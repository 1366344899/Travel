<template>
  <div>
    <div class="search">
      <input v-model="keyword" class="search-input" type="text" placeholder="输入城市名或拼音"/>
    </div>
    <div class="search-content" v-show="keyword" ref="search">
      <ul>
        <li class="search-item border-bottom" v-for="item of list" :key="item.id" @click="handleCityClick(item.name)">{{item.name}}</li>
      </ul>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  data () {
    return {
      keyword: '',
      list: []
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.search, {click: true})
  },
  props: {
    cities: Object
  },
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  watch: {
    keyword () {
      if (!this.keyword) {
        this.list = []
        return
      }
      const result = []
      for (let i in this.cities) {
        this.cities[i].forEach((value) => {
          if (value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword) > -1) {
            result.push(value)
          }
        })
      }
      this.list = result
    }
  }
}
</script>
<style lang="stylus" scoped>
@import '../../../styles/varible.styl'
.search
  height: .72rem
  padding: 0 .1rem
  background: $bgColor
  .search-input
    box-sizing: border-box
    width: 100%
    height: .62rem
    line-height: .62rem
    text-align: center
    border-radius: .06rem
    color: #666
    padding:0 .1rem
.search-content
  z-index: 1
  overflow: hidden
  position: absolute
  top: 1.58rem
  left: 0
  right: 0
  bottom: 0
  background: #eee
  .search-item
    line-height: .62rem
    padding-left: .2rem
    background: #fff
    color: #666
</style>
