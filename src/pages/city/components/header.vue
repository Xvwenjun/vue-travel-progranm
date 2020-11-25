<template>
<div class="head-wrap">
    国内城市
    <router-link to="./">
    <span class="iconfont back-city-icon">&#xe624;</span>
    </router-link>
</div>
</template>
<script> 
export default {
    name:"HomeCity"
}
</script>

<style lang="stylus" scoped>
 @import '~styles/varibles.styl'
 .head-wrap
  overflow:hidden
  position:relative
  height:$headerHeight
  line-height:$headerHeight
  background:$bgColor
  color:#fff
  font-size: .32rem
  text-align:center
  .back-city-icon
   position:absolute
   left:0
   top:0
   margin-left:.2rem
   color:#fff
</style>