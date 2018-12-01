<template>
    <div class="header">
        <div class="header-left">
        <span class="iconfont back-icon">&#xe624;</span>
        </div>
        <div class="header-input">
        <span class="iconfont">&#xe632;</span>
        输入城市/景点/游玩主题</div>
        <div class="header-right">
        城市
        <span class="iconfont arrow-icon">&#xe600;</span>
        </div>
    </div>
</template>
<script>
export default {
  name: 'HomeHeader'
}
</script>
<style lang="stylus" scoped>
@import '../../../styles/varible.styl'
  .header
    display: flex
    line-height: .86rem
    background: $bgColor
    color:#fff
    .header-left
      width: .64rem
      float: left
      padding-left: .2rem
      .back-icon
        text-align:center
        font-size: .4rem
    .header-input
      flex: 1
      line-height: .64rem
      margin-top: .12rem
      margin-left: .1rem
      margin-bottom: .1rem
      background: #fff
      border-radius: .1rem
      padding-left: .2rem
      color: #ccc
    .header-right
      width: 1.24rem
      float: right
      text-align: center
      .arrow-icon
        margin-left: .05rem
        font-size .25rem
</style>
