<template>
    <div class="icons">
        <swiper :options="swiperOption" v-if="iconList.length">
            <swiper-slide v-for="(page, index) of pages" :key="index">
                <div class="icon" v-for='item of page' :key="item.id">
                    <div class="icon-img-content">
                        <img class='icon-img' :src="item.imgUrl">
                    </div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
export default {
  props: {
    iconList: Array
  },
  data () {
    return {
      swiperOption: {
        loop: true
      }
    }
  },
  computed: {
    pages () {
      const pages = []
      this.iconList.forEach((item, index) => {
        const page = Math.floor(index / 8)
        if (!pages[page]) {
          pages[page] = []
        }
        pages[page].push(item)
      })
      return pages
    }
  }
}
</script>
<style lang="stylus" scoped>
.icons >>> .swiper-container
  height: 0
  padding-bottom: 50%
.icons
  margin-top: .1rem
  .icon
    position: relative
    overflow: hidden
    float: left
    width: 25%
    height: 0
    padding-bottom: 25%
    .icon-img-content
      display: block
      margin: 0 auto
      height: 100%
      .icon-img
        position: absolute
        top: -.1rem
        left: 0
        right: 0
        bottom: .24rem
        box-sizing: border-box
        padding: .2rem
        height: 100%
    .icon-desc
      position: absolute
      left: 0
      right: 0
      bottom: 0
      height: .34rem
      line-height: .44rem
      color: #333
      text-align: center
      overflow: hidden
      white-space: nowrap
      text-overflow: ellipsis
</style>
