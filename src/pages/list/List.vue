<template>
  <div class="container">
    <list-header></list-header>
    <list-content :list="list"></list-content>
  </div>
</template>

<script>
import ListHeader from '@/pages/list/components/Header'
import ListContent from '@/pages/list/components/Content'
import axios from 'axios'
  export default{
    name:'List',
    components: {
      ListHeader,
      ListContent
    },
    data() {
    return{
      list:[]
    }
  },
   methods: {
    getListInfo () {
      axios.get('/api/detail.json').then(this.getListInfoSucc)
    },
    getListInfoSucc (res) {
      res = res.data
      if(res.ret && res.data){
        const data = res.data
        this.list = data.list
      }
    }
  },
  mounted() {
    this.getListInfo()
  }
  }
</script>

<style lang="stylus" scoped>
  .container
    background-color: #f5f5f5
</style>