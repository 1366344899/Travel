<template>
    <div>
        <home-header></home-header>
        <HomeSwiper></HomeSwiper>
        <HomeIcons></HomeIcons>
    </div>
</template>
<script>
import HomeHeader from './components/header'
import HomeSwiper from './components/swiper'
import HomeIcons from './components/icons'
export default {
  components: {
    HomeHeader,
    HomeSwiper,
    HomeIcons
  }
}
</script>
<style>

</style>
