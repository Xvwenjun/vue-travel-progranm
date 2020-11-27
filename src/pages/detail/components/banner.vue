<template>
    <div class="banner"
     @click="handleBannerClick">
       <img class="banner-img" 
            src="https://imgs.qunarzz.com/p/p19/1809/b9/2a3d362aabcbb02.jpg_256x160_28907832.jpg">
       <div class="banner-info">
           <div class="banner-title">AAAAA</div>
           <div class="banner-number">
               <span class="iconfont banner-icon">&#xe603;</span>
               89
           </div>
       </div>
       <common-gallary 
       :imgs="imgs"
       v-if="gallaryOpen"
       @close="handleGallaryClose"
       ></common-gallary>
    </div>
</template>
<script>
import CommonGallary from 'common/Gallary/gallary'
export default {
    name:'DetailBanner',
    data(){
        return {
            gallaryOpen:false,
            imgs:["https://dss0.bdstatic.com/7Ls0a8Sm1A5BphGlnYG/sys/portrait/item/netdisk.1.11fa0a03.a_x_X6PQABO9hkBAi6pVnw.jpg","https://dss0.bdstatic.com/7Ls0a8Sm1A5BphGlnYG/sys/portrait/item/netdisk.1.11fa0a03.a_x_X6PQABO9hkBAi6pVnw.jpg"]
        }
    },
    components:{
        CommonGallary
    },
    methods:{
        handleBannerClick(){
            this.gallaryOpen = true
        },
        handleGallaryClose(){
             this.gallaryOpen = false
             console.log(this.gallaryOpen)
        }
    }
}
</script>

<style lang="stylus" scoped>
 .banner
  position:relative
  overflow:hidden
  height:0
  padding-bottom :55%
  .banner-img
   width:100%
  .banner-info
   display:flex
   position:absolute
   left:0
   bottom:0
   right:0
   line-height:.6rem
   color:#fff
   background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,0.8))
   .banner-title
    flex:1
    font-size:.32rem
    padding:0 .2rem
   .banner-number
    height:.32rem
    line-height:.32rem
    margin-top:.14rem
    padding:0 .4rem
    border-radius:.2rem
    background:rgba(0,0,0,.8)
    font-size:.24rem
    .banner-icon
     vertical-align:bottom
     font-size:.3rem
</style>