<template>
 <div class="header">
    <div class="header-left"> 
       <span class="iconfont back-icon">&#xe624;</span>
    </div>
    <div class="header-input"> 
      <span class="iconfont ">&#xe632;</span>
      输入城市/景点/游玩主题 </div>
      <router-link to="./city">
        <div class="header-right"> {{this.$store.state.city}}<span class="iconfont arrow-icon">&#xe60c;</span></div>
      </router-link>
 </div>
</template>

<script>
export default {
  name:"HomeHeader"
}

</script>


<style lang="stylus" scoped>
  @import '~styles/varibles.styl'
.header 
   display:flex
   background:$bgColor
   height:$headerHeight
   line-height:$headerHeight
   color:#fff  
  .header-left
      float:left
      width:.64rem 
     .back-icon
      text-align:center  
      margin-left:.2rem
      font-size:.4rem
  .header-input
      flex:1
      background :#fff
      color:#ccc
      border-radius:.1rem
      margin-top:.12rem
      margin-left:.2rem
      padding-left:.2rem
      height:.64rem
      line-height:.64rem
  .header-right
      float:right
      width:1.24rem
      text-align:center
      color:#fff
      .arrow-icon
        font-size:.2rem

</style>