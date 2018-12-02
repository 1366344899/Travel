<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
      <img class="swiper-img" :src="item.imgurl" />
      </swiper-slide>
      <div class="swiper-pagination"  slot="pagination"></div>
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
      swiperList: [{
        id: '001',
        imgurl: 'https://imgs.qunarzz.com/p/tts1/1805/c2/ca860cb21c2c9c02.jpg_r_390x260x90_6d2d1c16.jpg'
      },
      {
        id: '002',
        imgurl: 'https://imgs.qunarzz.com/p/tts8/1703/94/61eb7ce216efc702.jpg_r_390x260x90_d5dd6341.jpg'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
  background: white
.wrapper
 width: 100%
 overflow: hidden
 height: 0
 padding-bottom: 31.25%
 .swiper-img
  width: 100%
</style>
