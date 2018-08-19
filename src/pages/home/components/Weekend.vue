<template>
  <div class="weekend">
    <div class="weekend-title">周末去哪</div>
    <ul v-for="item of weekendList" :key="item.id">
      <li class="item">
        <div class="item-img">
          <img class="item-img-content" :src="item.imgUrl">
        </div>
        <div class="item-info">
          <p class="item-info-title">{{item.title}}</p>
          <p class="item-info-desc">{{item.desc}}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HomeWeekend',
  props: {
    weekendList:Array
  }
}

</script>


<style lang="stylus" scoped>
  @import '~styles/mixins.styl'
  .weekend
    margin-top:.2rem
    background-color:#fff
    .weekend-title
      margin-top:.2rem
      line-height:.8rem
      text-indent:.3rem
      font-size:.32rem
    .item
      padding-top:.1rem
      .item-img
        overflow:hidden
        width:100%
        height:0
        padding-bottom:37.4375%
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
</style>