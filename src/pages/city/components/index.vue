<template>
  <ul class="list">
    <li class="item" v-for="(item,key) of cities" :key="key">{{key}}</li>
  </ul>
</template>
<script>
export default {
  props: {
    cities: Object
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
