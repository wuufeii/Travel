<template>
  <div class="recommend">
    <div class="recommend-title">热销推荐</div>
    <ul v-for="item of recommendList" :key="item.id">
      <li class="item">
        <img class="item-img" :src="item.imgUrl">
        <div class="item-info">
          <p class="item-info-title">{{item.title}}</p>
          <p class="item-info-desc">{{item.desc}}</p>
          <button class="item-button">查看详情</button>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeRecommend',
  props:{
    recommendList:Array
  }
}
</script>


<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .recommend
    margin-top:.2rem
    background-color:#fff
    .recommend-title
      margin-top:.2rem
      line-height:.8rem
      text-indent:.3rem
      font-size:.32rem
    .item
      display:flex
      height:1.9rem
      padding-top:.1rem
      padding-bottom:.1rem
      border-bottom:.018rem solid #ccc
      .item-img
        width:1.7rem
        height:1.7rem
        padding:.1rem
      .item-info
        flex:1
        padding-left:.1rem
        min-width:0
        .item-info-title
          font-size:.30rem
          line-height:.6rem
          ellipsis()
        .item-info-desc
          font-size:.26rem
          line-height:.5rem
          color:#777
          ellipsis()
        .item-button
          line-height:.46rem
          margin-top:.16rem
          background-color:#ff9300
          padding:0 .2rem
          color:#fff

</style>