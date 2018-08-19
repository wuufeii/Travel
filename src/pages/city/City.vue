<template>
  <div>
    <city-header></city-header>
    <city-search></city-search>
    <city-list :hotCites="hotCities" :cities="cities"></city-list>
    <city-alphabet :cities="cities"></city-alphabet>
  </div>
</template>


<script>
  import axios from 'axios'
  import CityHeader from './components/Header'
  import CitySearch from './components/Search'
  import CityList from './components/List'
  import CityAlphabet from './components/Alphabet'
  export default{
    name:'City',
    components:{
      CityHeader,
      CitySearch,
      CityList,
      CityAlphabet
    },
    data() {
      return{
         hotCities:[],
         cities:{}
      }
    },
    methods:{
      getCityInfo() {
        axios.get('/api/city.json').then(this.getCityInfoSucc)
      },
      getCityInfoSucc(res) {
        res = res.data
        if(res.ret && res.data){
          const data = res.data
          this.cities = data.cities
          this.hotCities = data.hotCities
        }
        console.log(res)
      }
    },
    mounted() {
    this.getCityInfo()
  }
  }
</script>

<style lang="stylus" scoped>
  
</style>