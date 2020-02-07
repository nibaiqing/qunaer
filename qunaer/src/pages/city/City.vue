<template>
  <div>
    <city-header @change="handleHeaderHeight"></city-header>
    <city-search @change="handleSearchHeight" :cities="cities"></city-search>
    <city-list
      :hot="hotCities"
      :cities="cities"
      :letter="letter"
    ></city-list>
    <city-alphabet
      :cities="cities"
      :header="headerHeight"
      :search="searchHeight"
      @change="handleLetterChange"
    ></city-alphabet>
  </div>
</template>
<script>
import CityHeader from './components/Header'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: 'City',
  components: {
    CityHeader,
    CitySearch,
    CityList,
    CityAlphabet
  },
  data () {
    return {
      hotCities: [],
      cities: {},
      letter: '',
      headerHeight: 0,
      searchHeight: 0
    }
  },
  methods: {
    getCityData () {
      axios.get('/api/city.json').then(this.getCityDataSucc)
    },
    getCityDataSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.hotCities = data.hotCities
        this.cities = data.cities
      }
    },
    handleLetterChange (letter) {
      this.letter = letter
    },
    handleHeaderHeight (header) {
      this.headerHeight = header
    },
    handleSearchHeight (search) {
      this.searchHeight = search
    }
  },
  mounted () {
    this.getCityData()
  }
}
</script>
<style lang="stylus" scoped>

</style>
