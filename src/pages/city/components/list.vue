<template>
  <div class="list" ref="wrapper">
    <div>
        <div class="area">
        <div class="title border-topbottom">当前城市</div>
        <div class="button-list">
            <div class="button-wrapper">
            <div class="button">
                {{this.$store.state.city}}
            </div>
            </div>
        </div>
        </div>
        <div class="area">
            <div class="title border-topbottom">热门城市</div>
            <div class="button-list">
                <div class="button-wrapper" v-for='item of HotCities' :key="item.id" @click="handleCityClick(item.name)">
                    <div class="button">
                        {{item.name}}
                    </div>
                </div>
            </div>
         </div>
        <div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
            <div class="title border-topbottom">{{key}}</div>
            <div class="item-list" >
                <div class="item border-bottom" v-for="inneritem of item" :key="inneritem.id" @click="handleCityClick(inneritem.name)">
                {{inneritem.name}}
                </div>
            </div>
        </div>
    </div>
  </div>
</template>
<script>
import Bscroll from 'better-scroll'
export default {
  methods: {
    handleCityClick (city) {
      this.$store.commit('changeCity', city)
      this.$router.push('/')
    }
  },
  mounted () {
    this.scroll = new Bscroll(this.$refs.wrapper, {click: true})
  },
  props: {
    HotCities: Array,
    cities: Object,
    letter: String
  },
  watch: {
    letter () {
      if (this.letter) {
        const element = this.$refs[this.letter][0]
        this.scroll.scrollToElement(element)
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
.border-topbottom
  :before
    border-color: #ccc
  :after
    border-color: #ccc
.border-bottom
  :before
    border-color: #ccc
.list
  overflow: hidden
  position: absolute
  top: 1.58rem
  left: 0
  right: 0
  bottom: 0
  .title
    line-height: .54rem
    background: #eee
    padding-left: .2rem
    color: #666
    font-size: .26rem
  .button-list
    padding: .1rem .6rem .1rem .1rem
    overflow: hidden
    .button-wrapper
      float: left
      width: 33.33%
      .button
        margin: .1rem
        text-align: center
        border: .022rem solid #ccc
        border-radius: .06rem
        font-size: .25rem
  .item-list
    .item
      line-height: .55rem
      padding-left: .3rem
</style>
