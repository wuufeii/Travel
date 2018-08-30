<template>
  <div>
    <detail-banner
      :sightName="sightName"
      :bannerImg="bannerImg"
      :bannerImgs="bannerImgs">
    </detail-banner>
    <detail-header></detail-header>
    <div class="content">
      <detail-list :list="list"></detail-list>
    </div>
  </div>
</template>


<script>
import DetailBanner from './components/Banner'
import DetailHeader from './components/Header'
import DetailList from './components/List'
import axios from 'axios'
export default{
  name: 'Detail',
  components:{
    DetailBanner,
    DetailHeader,
    DetailList
  },
  data() {
    return{
      sightName:'',
      bannerImg:'',
      bannerImgs: [],
      list:[]
    }
  },
  methods: {
    getDetailiInfo() {
      axios.get('/api/detail.json',{
        params: {
          id:this.$route.params.id
        }
      }).then(this.handleDataSuccess)
    },
    handleDataSuccess(res) {
      res = res.data
      if(res.ret  && res.data){
        const data = res.data
        this.sightName = data.sightName
        this.bannerImg = data.bannerImg
        this.bannerImgs = data.gallaryImgs
        this.list = data.categoryList
      }
    }
  },
  mounted() {
    this.getDetailiInfo()
  },
  activated() {
    this.getDetailiInfo()
  }
}

</script>

<style lang="stylus" scoped>
.content
  min-height:50rem
</style>