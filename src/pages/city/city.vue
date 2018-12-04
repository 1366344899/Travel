<template>
  <div>
    <CityHeader></CityHeader>
    <CitySearch></CitySearch>
    <CityList></CityList>
    <CityIndex></CityIndex>
  </div>
</template>
<script>
import CityHeader from './components/header'
import CitySearch from './components/search'
import CityList from './components/list'
import CityIndex from './components/index'
export default {
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityIndex
  }
}
</script>
<style lang="stylus" scoped>

</style>
