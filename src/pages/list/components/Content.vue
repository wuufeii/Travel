<template>
  <div class="item-box">
    <div class="item" v-for="item of list" :key="item.id">
      <div class="item-container">
        <div class="item-img">
          <img class="item-img-con" :src="item.imgUrl" :alt="item.title">
        </div>
        <div class="item-content">
          <div class="item-content-title">{{item.title}}</div>
          <div class="item-content-desc">
            <span class="item-content-desc-star">★★★★★</span>
            <span class="item-content-desc-comment">{{item.number}}条评价</span>
          </div>
          <div class="item-content-price">
            <span class="money-flag">￥</span>
            <span class="money-content">{{item.price}}</span>
            <span class="money-small">起</span>
            <span class="area">{{item.area}}</span>
          </div>
          <div class="item-content-flag">
            <span class="flag-detail">古建筑</span>
          </div>
        </div>
      </div>
      <div class="type">
        <div class="type-left">
          {{item.moring}}
        </div>
        <div class="type-right">
          <span>￥</span>
          <span class="money-content">{{item.sales}}</span>
        </div>
      </div>
      <div class="type">
        <div class="type-left">
          {{item.afternoon}}
        </div>
        <div class="type-right">
          <span>￥</span>
          <span class="money-content">{{item.normal}}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default{
    name:'ListContent',
    props:{
      list:Array
    }
  }
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.item-box
  padding-top:$headerHeight
  .item
    height:0
    padding-bottom:4.32rem
    margin-bottom:.2rem
    background-color:#fff
    overflow:hidden
    .item-container
      overflow:hidden
      padding:.2rem .22rem
      .item-img
        float:left
        width:2rem
        height:2rem
        overflow:hidden
        .item-img-con
          width:100%
      .item-content
        width:calc(100% - 2.2rem)
        height:2rem
        overflow:hidden
        float:left
        padding-left:.2rem
        .item-content-title
          overflow: hidden
          height: .44rem
          color: #212121
          font-size: .32rem
          line-height: .44rem
          white-space: nowrap
          text-overflow: ellipsis
        .item-content-desc
          margin-top: .14rem
          height: .34rem
          line-height: .34rem
          .item-content-desc-star
            color: #ffb436
            font-size:.3rem
          .item-content-desc-comment
            color: #616161
            font-size: .24rem
        .item-content-price
          display:block
          overflow:hidden
          margin-top:.18rem
          .money-flag
            height: .36rem;
            color: #ff8300;
            font-size: .2rem;
            line-height: .4rem;
          .money-content
            height: .36rem;
            color: #ff8300;
            font-size: .36rem;
            line-height: .4rem;
            padding-right:.02rem
          .money-small
            font-size:.24rem
            color:#616161
          .area
            float:right
            color: #616161;
            font-size:.24rem
            white-space: nowrap
            padding-top:.12rem
        .item-content-flag
          margin-top:.1rem
          .flag-detail
            margin-right:.08rem
            color:#00afc7
            display: inline-block;
            font-size:.2rem
            padding:.044rem
            border:.01rem solid #00afc7
            border-radius:.08rem
  .type
    position: relative;
    height: .96rem;
    margin-left: .2rem;
    border-top:.012rem solid #e0e0e0 
    .type-left
      overflow: hidden;
      margin-right: 1.4rem;
      height: .96rem;
      color: #616161;
      font-size: .28rem;
      line-height: .96rem;
      white-space: nowrap;
      text-overflow: ellipsis;
    .type-right
      overflow: hidden;
      position: absolute;
      top: 0;
      right: .2rem;
      width: 1.2rem;
      height: .96rem;
      color: #ff8300;
      font-size: .2rem;
      line-height: .96rem;
      text-align: right;
      .money-content
        font-size: .32rem;
        margin-left:-.04rem
</style>