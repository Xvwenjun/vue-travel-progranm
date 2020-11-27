<template>
    <div class="banner"
     @click="handleBannerClick">
       <img class="banner-img" 
            :src="bannerImg">
       <div class="banner-info">
           <div class="banner-title">{{this.sightName}}</div>
           <div class="banner-number">
               <span class="iconfont banner-icon">&#xe603;</span>
               {{this.gallaryImgs.length}}
           </div>
       </div>
       <common-gallary 
       :imgs="gallaryImgs"
       v-if="gallaryOpen"
       @close="handleGallaryClose"
       ></common-gallary>
    </div>
</template>
<script>
import CommonGallary from 'common/Gallary/gallary'
export default {
    name:'DetailBanner',
    props:{
        sightName:String,
        bannerImg:String,
        gallaryImgs:Array
    },
    data(){
        return{
            gallaryOpen:false
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