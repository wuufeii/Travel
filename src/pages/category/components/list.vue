<template>
  <div class="list">
    <ul v-for="item of categoryList" :key="item.id">
      <li class="item">
        <div class="item-img">
          <img class="item-img-content" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-info-title">{{item.title}}</p>
          <p class="item-info-desc">{{item.desc}}</p>
        </div>
        <div class="item-price" v-if="item.price">
          <span class="item-price-detail">￥{{item.price}}</span>
          <span class="item-price-span">起</span>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    categoryList:Array
  }
}

</script>

<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .list
    background-color:#fff
    .item
      position:relative
      .item-img
        overflow:hidden
        width:100%
        height:0
        padding-bottom:43.37288%
        .item-img-content
          width:100%
      .item-info
        padding-left:.3rem
        padding-top:.1rem
        .item-info-title
          font-size:.30rem
          line-height:.5rem
          overflow: hidden;
          padding-right: 1.4rem;
          color: #212121;
          ellipsis()
        .item-info-desc
          font-size:.26rem
          line-height:.5rem
          color:#777
          ellipsis()
      .item-price
        position:absolute
        bottom:.5rem
        right:.2rem
        .item-price-detail
          font-size:.4rem
          font-weight:bold
          color:#ff8300
          padding-right:.01rem
        .item-price-span
          color:#616161
          font-size:.22rem
</style>