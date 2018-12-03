<template>
    <div>
        <div class='title'>热门推荐</div>
        <ul>
            <li class="item" v-for="item of recommendList" :key="item.id">
                <div class="item-img-wrapper">
                    <img class="item-img" :src='item.imgUrl' />
                </div>
                <div class="item-info border-botton">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  props: {
    recommendList: Array
  }
}
</script>
<style lang="stylus" scoped>
  .title
    background: #eee
    line-height: .8rem
    text-indent: .2rem
    margin-top: .2rem
  .item
    display: flex
    height: 1.9rem
    overflow: hidden
    .item-img
      width:1.7rem
      height: 1.7rem
      padding: .1rem
    .item-info
      flex: 1
      padding: .1rem
      min-width: 0
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
      .item-button
        background: #ff9300
        padding: 0 .1rem
        border-radius: .06rem
        margin-top: .20rem
        line-height: .44rem
        color: #fff
</style>
