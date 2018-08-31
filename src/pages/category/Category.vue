<template>
  <div class="container">
    <category-header></category-header>
    <category-list :cityAreaList="cityAreaList"></category-list>
  </div>
</template>

<script>
import CategoryHeader from './components/Header'
import CategoryList from './components/List'
import axios from 'axios'
export default{
  name: 'Category',
  components:{
    CategoryHeader,
    CategoryList
  },
   data() {
    return{
      cityAreaList:[]
    }
  },
   methods: {
    getCategoryInfo () {
      axios.get('/api/detail.json').then(this.getCategoryInfoSucc)
    },
    getCategoryInfoSucc (res) {
      res = res.data
      if(res.ret && res.data){
        const data = res.data
        this.cityAreaList = data.cityAreaList
      }
    }
  },
  mounted() {
    this.getCategoryInfo()
  }
}

</script>

<style lang="stylus" scoped>
  .container
    background-color:#f5f5f5
</style>