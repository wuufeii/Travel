<template>
  <div class="wrapper">
    <swiper :options="swiperOption">
      <swiper-slide v-for="item of swiperList" :key="item.id">
        <img class="swiper-img" :src="item.imgUrl">
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>


<script>
export default{
  name: 'HomeSwiper',
  data() {
    return{
      swiperOption:{
        pagination:'.swiper-pagination',
        loop:true
      },
      swiperList:[{
        id:'001',
        imgUrl:'http://img1.qunarzz.com/piao/fusion/1806/3c/c72a1ccd4d7b2202.jpg_750x200_b88bbab4.jpg'
      },{
        id:'002',
        imgUrl:'http://img1.qunarzz.com/piao/fusion/1801/bd/04554e7c67650302.jpg_750x200_4293d60a.jpg'
      }]
    }
  }
}
</script>

<style lang="stylus" scoped>
  .wrapper >>> .swiper-pagination-bullet-active
    background-color:#fff
  .wrapper
    overflow:hidden
    width:100%
    height:0
    padding-bottom:26.66666667%
    background-color:#eee
    .swiper-img
      width:100%
</style>