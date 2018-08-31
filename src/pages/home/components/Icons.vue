<template>
  <div class="icons">
    <swiper :options="swiperOption">
      <swiper-slide v-for="(page,index) of pages" :key="index">
        <router-link to="/list" tag="div" class="icon" v-for="item of page" :key="item.id">
          <div class="icon-img">
            <img class="icon-img-content" :src="item.imgUrl">
          </div>
          <p class="icon-desc">{{item.desc}}</p>
        </router-link>
      </swiper-slide>
      <div class="swiper-pagination" slot="pagination"></div>
    </swiper>
  </div>
</template>



<script>
  export default{
    name: 'HomeIcons',
    props:{
      iconList:Array
    },
    data() {
      return{
        swiperOption:{
        pagination:'.swiper-pagination',
        autoplay:false
      }
      }
    },
    computed: {
      pages () {
        const pages = []
        this.iconList.forEach((item,index) => {
          const page = Math.floor(index / 8)
          if(!pages[page]){
          pages[page] = []
        }
        pages[page].push(item)
        })
        return pages
      }
    }
  }
</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  @import '~styles/mixins.styl'
  .icons >>> .swiper-container
    height: 0
    padding-bottom: 56%
  .icons >>> .swiper-pagination-bullet
    width:6px
    height:6px
  .icons
    overflow:hidden
    height:0
    padding-top:1%
    padding-bottom:55%
    background-color:#fff
    .icon
      overflow:hidden
      position:relative
      float:left
      width:25%
      height:0
      padding-bottom:25%
      .icon-img
        position:absolute
        top: 0.2rem;
        left: .2rem;
        right: .2rem;
        bottom: 0.55rem;
        .icon-img-content
          height:100%
          display:block
          margin:0 auto
      .icon-desc{
        position:absolute
        bottom:0
        left:0
        right:0
        height:.44rem
        line-height:.44rem
        text-align:center
        color:$darkTextColor
        ellipsis()
      }
</style>