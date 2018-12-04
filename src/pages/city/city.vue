<template>
  <div>
    <CityHeader></CityHeader>
    <CitySearch></CitySearch>
    <CityList :cities="cities" :HotCities="HotCities" :letter="letter"></CityList>
    <CityIndex :cities="cities" @change="handleChange"></CityIndex>
  </div>
</template>
<script>
import CityHeader from './components/header'
import CitySearch from './components/search'
import CityList from './components/list'
import CityIndex from './components/index'
import axios from 'axios'
export default {
  data () {
    return {
      cities: {},
      HotCities: [],
      letter: ''
    }
  },
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityIndex
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json').then(this.handleGetCityInfoSucc)
    },
    handleGetCityInfoSucc (res) {
      console.log(res)
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.HotCities = data.hotCities
      }
    },
    handleChange (letter) {
      this.letter = letter
    }
  },
  mounted () {
    this.getCityInfo()
  }
}
</script>
<style lang="stylus" scoped>

</style>
