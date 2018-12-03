<template>
    <div>
        <div class='title'>周末去哪</div>
        <ul>
            <li class="item" v-for="item of weekendList" :key="item.id">
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
  props: {
    weekendList: Array
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
      color: #bbb
      overflow: hidden
      white-space: nowrap
      text-overflow: ellipsis
</style>
