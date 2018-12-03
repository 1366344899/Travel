<template>
    <div class="icons">
        <swiper :options="swiperOption">
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
  data () {
    return {
      swiperOption: {
        pagination: '.swiper-pagination',
        loop: true
      },
      iconList: [{
        id: '001',
        imgUrl: '//img.alicdn.com/tfs/TB1qpwlQXXXXXcCXXXXXXXXXXXX-256-256.png_60x60.jpg_.webp',
        desc: '景点门票1景点门票1景点门票1景点门票1'
      }, {
        id: '002',
        imgUrl: '//img.alicdn.com/tfs/TB1qpwlQXXXXXcCXXXXXXXXXXXX-256-256.png_60x60.jpg_.webp',
        desc: '景点门票2'
      }, {
        id: '003',
        imgUrl: '//img.alicdn.com/tfs/TB1qpwlQXXXXXcCXXXXXXXXXXXX-256-256.png_60x60.jpg_.webp',
        desc: '景点门票3'
      }, {
        id: '004',
        imgUrl: '//img.alicdn.com/tfs/TB1qpwlQXXXXXcCXXXXXXXXXXXX-256-256.png_60x60.jpg_.webp',
        desc: '景点门票4'
      }, {
        id: '005',
        imgUrl: '//img.alicdn.com/tfs/TB1qpwlQXXXXXcCXXXXXXXXXXXX-256-256.png_60x60.jpg_.webp',
        desc: '景点门票5'
      }, {
        id: '006',
        imgUrl: '//img.alicdn.com/tfs/TB1qpwlQXXXXXcCXXXXXXXXXXXX-256-256.png_60x60.jpg_.webp',
        desc: '景点门票6'
      }, {
        id: '007',
        imgUrl: '//img.alicdn.com/tfs/TB1qpwlQXXXXXcCXXXXXXXXXXXX-256-256.png_60x60.jpg_.webp',
        desc: '景点门票7'
      }, {
        id: '008',
        imgUrl: '//img.alicdn.com/tfs/TB1qpwlQXXXXXcCXXXXXXXXXXXX-256-256.png_60x60.jpg_.webp',
        desc: '景点门票8'
      }, {
        id: '009',
        imgUrl: '//img.alicdn.com/tfs/TB1qpwlQXXXXXcCXXXXXXXXXXXX-256-256.png_60x60.jpg_.webp',
        desc: '景点门票9'
      }]
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
  width: 100%
  overflow: hidden
  height: 0
  padding-bottom: 50%
  .icon
    position: relative
    overflow: hidden
    float: left
    width: 25%
    height: 0
    padding-bottom: 25%
    .icon-img
      position: absolute
      top: -.1rem
      left: 0
      right: 0
      bottom: .24rem
      box-sizing: border-box
      padding: .2rem
      .icon-img-content
        display: block
        margin: 0 auto
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
