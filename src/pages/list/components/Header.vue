<template>
  <div class="header">
    <router-link to="/" tag="div" class="header-left">
      <span class="iconfont back-icon">&#xe624;</span>
    </router-link>
    <div class="header-input">
      <span class="iconfont">&#xe632;</span> 输入城市或景点
    </div>
      <div class="header-right">
        搜索
      </div>
  </div>
</template>


<script>
export default{
  name: 'ListHeader',
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.header
  display:flex
  line-height:$headerHeight
  background:#fff
  border-bottom:.012rem solid #e0e0e0
  width:100%
  position:fixed
  z-index:1
  .header-left
    width:.64rem
    float:left
    .back-icon
      display:block
      font-size:.32rem
      font-weight:bold
      text-align:center
  .header-input
    flex:1
    height:.58rem
    line-height.58rem
    margin-top:.14rem
    margin-left:.18rem
    padding-left:.2rem
    background-color:#f2f2f2
    border-radius:.32rem
    color:#ccc
    text-align:center
  .header-right
    min-width:.8rem
    padding:0 .1rem
    float:right
    text-align:center
    color:#212121
    .arrow-icon
      font-size:.24rem
      margin-left:-.04rem
</style>
