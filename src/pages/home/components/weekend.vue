<template>
    <div>
        <div class='title'>周末去哪</div>
        <ul>
            <li class="item" v-for="item of recommendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img class="item-img" :src='item.imgUrl' />
                </div>
                <div class="item-info border-botton">
                    <p class="item-title">{{item.titile}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  data () {
    return {
      recommendList: [{
        id: '001',
        imgUrl: 'https://imgs.qunarzz.com/p/tts8/1703/94/61eb7ce216efc702.jpg_r_390x260x90_d5dd6341.jpg',
        titile: '中国好声音中国好声音中国好声音中国好声音',
        desc: '中国好声音中国好声音中国好声音中国好声音中国好声音中国好声音'
      },
      {
        id: '002',
        imgUrl: 'https://imgs.qunarzz.com/p/tts8/1703/94/61eb7ce216efc702.jpg_r_390x260x90_d5dd6341.jpg',
        titile: '中国好声音中国好声音中国好声音中国好声音',
        desc: '中国好声音中国好声音中国好声音中国好声音中国好声音中国好声音'
      },
      {
        id: '003',
        imgUrl: 'https://imgs.qunarzz.com/p/tts8/1703/94/61eb7ce216efc702.jpg_r_390x260x90_d5dd6341.jpg',
        titile: '中国好声音中国好声音中国好声音中国好声音',
        desc: '中国好声音中国好声音中国好声音中国好声音中国好声音中国好声音'
      },
      {
        id: '004',
        imgUrl: 'https://imgs.qunarzz.com/p/tts8/1703/94/61eb7ce216efc702.jpg_r_390x260x90_d5dd6341.jpg',
        titile: '中国好声音中国好声音中国好声音中国好声音',
        desc: '中国好声音中国好声音中国好声音中国好声音中国好声音中国好声音'
      }]
    }
  }
}
</script>
<style lang="stylus" scoped>
  .title
    background: #eee
    line-height: .8rem
    text-indent: .2rem
    margin-top: .2rem
  .item-img-wrapper
    height: 0
    overflow: hidden
    padding-bottom: 33.9%
    .item-img
      width: 100%
  .item-info
    padding: .1rem
    .item-title
      line-height: .54rem
      font-size: .32rem
      overflow: hidden
      white-space: nowrap
      text-overflow: ellipsis
    .item-desc
      line-height: .32rem
      color: #ccc
      overflow: hidden
      white-space: nowrap
      text-overflow: ellipsis
</style>
