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
  data() {
    return {
      weekendList: [{
        id: '001',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1507/8e/f41005646c1e8e.jpg_r_640x214_65f25f65.jpg',
        title: '快乐湿身，水上狂欢',
        desc: '“快乐湿身，水上狂欢”门票低至5折起'
      }, {
        id: '002',
        imgUrl: 'http://img1.qunarzz.com/sight/source/1505/5f/276ed6784d25ee.jpg_r_640x214_2193082e.jpg',
        title: '重庆优质汤泉',
        desc: '细数重庆那些最赞的温泉'
      }]
    }

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
      height:4rem
      padding-top:.1rem
      padding-bottom:.1rem
      border-bottom:.018rem solid #ccc
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