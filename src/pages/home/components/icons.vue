<template>
<div class="icons">
   <swiper :options="swiperOptions">
       <swiper-slide v-for="(page,index) of pages" :key="index">
         <div class="icon" v-for="item of page" :key="item.id">
            <div class="icon-image">
               <img class="icon-image-content" :src="item.imgUrl">
            </div>
            <p class="icon-text">{{item.desc}}</p>
         </div>
       </swiper-slide>
     
   </swiper>
   
</div>
</template>

<script>
export default {
name:"HomeIcons",
props:{
list:Array
},
data(){
return {
  swiperOptions:{
      autoPlay:false
  }    
   }
},
computed:{
   pages(){
      const pages=[]
      this.list.forEach((item,index)=> {
        const page = Math.floor(index/8)
         if(!pages[page]){
               pages[page]=[]
         }
        pages[page].push(item)
      });
      return pages
   }
}
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl';
@import '~styles/mixins.styl';
.icons>>>.swiper-container
 margin-top:.1rem
 width:100%
 height:0
 padding-bottom:50%
 overflow:hidden
 .icon
  float:left
  position:relative
  height:0
  width:25%
  padding-bottom:25%
  box-sizing:border-box
  .icon-image
   position:absolute
   top:0
   left:0
   right:0
   bottom:.44rem
   padding:.1rem
   .icon-image-content
    display:block
    height:100%
    margin:0 auto
  .icon-text
   position:absolute
   bottom:0
   left:0
   right:0
   hieght:.44rem
   line-height:.44rem
   text-align:center
   conlor:$darkTextColor
   ellipsis()
</style> 