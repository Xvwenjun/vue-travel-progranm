<template>
<div class="icons">
   <swiper>
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
data(){
   return {
   iconList:[{
      id:'0001',
      imgUrl:'https://s.qunarzz.com/homenode/images/touchheader/flight.png',
      desc:'景点门票'
   },
   {
      id:'0002',
      imgUrl:'https://s.qunarzz.com/homenode/images/touchheader/hotel.png',
      desc:'吃喝玩乐'
   },
   {
      id:'0003',
      imgUrl:'https://s.qunarzz.com/homenode/images/touchheader/package.png',
      desc:'度假'
   },
   {
      id:'0004',
      imgUrl:'https://s.qunarzz.com/homenode/images/touchheader/package.png',
      desc:'度假'
   },
   {
      id:'0005',
      imgUrl:'https://s.qunarzz.com/homenode/images/touchheader/package.png',
      desc:'度假'
   },
   {
      id:'0006',
      imgUrl:'https://s.qunarzz.com/homenode/images/touchheader/package.png',
      desc:'度假'
   },
   {
      id:'0007',
      imgUrl:'https://s.qunarzz.com/homenode/images/touchheader/package.png',
      desc:'度假'
   },
   {
      id:'0008',
      imgUrl:'https://s.qunarzz.com/homenode/images/touchheader/package.png',
      desc:'度假'
   },
   {
      id:'0009',
      imgUrl:'https://s.qunarzz.com/homenode/images/touchheader/package.png',
      desc:'度假玩游戏唱歌'
   }
   ]
      }
   },
computed:{
   pages(){
      const pages=[]
      this.iconList.forEach((item,index)=> {
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