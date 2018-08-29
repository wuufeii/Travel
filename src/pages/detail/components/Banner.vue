<template>
  <div>
    <div class="banner" @click="handleBannerClick">
    <img class="banner-img" :src="bannerImg">
    <div class="banner-info">
      <div class="banner-title">{{this.sightName}}</div>
      <div class="banner-number">
        <span class="iconfont banner-icon">&#xe67b;</span>{{this.bannerImgs.length}}
      </div>
    </div>
  </div>
  <fade-animation>
    <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallayClose"></common-gallary>
  </fade-animation>
  </div>
  
</template>

<script>
import CommonGallary from 'common/gallary/Gallary'
import FadeAnimation from 'common/fade/FadeAnimation'
  export default{
    name: 'DetailBanner',
    props:{
      sightName: String,
      bannerImg: String,
      bannerImgs: Array
    },
    data() {
      return{
        imgs:['http://img1.qunarzz.com/sight/p0/1609/7a/7ae8ee7831836095a3.water.jpg_600x330_5d562f69.jpg','http://img1.qunarzz.com/sight/p0/1609/7a/7ae8ee7831836095a3.water.jpg_600x330_5d562f69.jpg'],
        showGallary:false
      }
    },
    components: {
      CommonGallary,
      FadeAnimation
    },
    methods: {
      handleBannerClick() {
        this.showGallary = true
      },
      handleGallayClose() {
        this.showGallary = false
      }
    }
  }
</script>

<style lang="stylus" scoped>
  .banner
    position:relative
    overflow:hidden
    height:0
    padding-bottom:55%
  .banner-img
    width:100%
  .banner-info
    display:flex
    position:absolute
    left:0
    right:0
    bottom:0
    color:#fff
    line-height:.6rem
    background-image: linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8))
    .banner-title
      flex:1
      font-size:.32rem
      padding:0 .2rem
    .banner-number
      height:.32rem
      line-height:.4rem
      margin-top:.14rem
      padding:0 .4rem
      height:.32rem
      line-height:.4rem
      border-radius:.2rem
      background:rgba(0,0,0,.8)
      font-size:.24rem
      .banner-icon
        font-size:.24rem
</style>