<template>
  <div>
    <city-head></city-head>
    <city-search></city-search>
    <city-list :cities = "cities" :hotCities="hotCities" :letter="letter"></city-list>
    <city-alphabet :cities = "cities" @change="getLetter"></city-alphabet>
  </div>
</template>

<script>

import CityHead from './components/CityHead'
import CitySearch from './components/Search'
import CityList from './components/List'
import CityAlphabet from './components/Alphabet'
import axios from 'axios'
export default {
  name: 'City',
  components: {CityHead, CitySearch, CityList, CityAlphabet},
  data () {
    return {
      cities: {},
      hotCities: [],
      letter: ''
    }
  },
  mounted () {
    this.getCityInfo()
  },
  methods: {
    getCityInfo () {
      axios.get('/api/city.json').then(this.CityInfoSucc)
    },
    CityInfoSucc (res) {
      res = res.data
      if (res.ret && res.data) {
        const data = res.data
        this.cities = data.cities
        this.hotCities = data.hotCities
      }
    },
    getLetter (letter) {
      // console.log(letter)
      this.letter = letter
    }
  }
}
</script>

<style lang="stylus" scoped></style>
