<template>
  <div>
    <div class="header-fixed" >
      <router-link to="/">
        <div class="iconfont header-fixed-back">&#xe624;</div>
      </router-link>
      <span>北京必游TOP10</span>
    </div>
  </div>
</template>

<script>
export default{
  name: 'CategoryHeader',
}

</script>

<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
  .header-fixed
    height:$headerHeight
    line-height:$headerHeight
    text-align:center
    color:#fff
    background-color:$bgColor
    font-size:.32rem
  .header-fixed-back
    position:absolute
    top:0
    left:0
    width:.64rem
    text-align:center
    font-size:.4rem
    color:#fff
</style>