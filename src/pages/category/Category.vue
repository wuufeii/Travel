<template>
  <div>
    <category-header></category-header>
    <category-list :categoryList="categoryList"></category-list>
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
      categoryList:[]
    }
  },
   methods: {
    getCategoryInfo () {
      axios.get('/api/index.json').then(this.getCategoryInfoSucc)
    },
    getCategoryInfoSucc (res) {
      res = res.data
      if(res.ret && res.data){
        const data = res.data
        this.categoryList = data.categoryList
      }
    }
  },
  mounted() {
    this.getCategoryInfo()
  }
}

</script>

<style lang="stylus" scoped>
</style>