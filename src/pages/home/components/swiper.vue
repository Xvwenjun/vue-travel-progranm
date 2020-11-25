<template>
<div class="wrap">
     <swiper :options="swiperOptions"  v-if="showSwiper">
       <swiper-slide v-for="item of list" :key="item.id">
           <img class="swiper-image" alt="" :src="item.imgUrl">
        </swiper-slide>
       <div class="swiper-pagination" slot="pagination"></div>
   </swiper>
</div>
</template>
<script>
export default {
    name:"HomeSwiper",
    props:{
        list:Array
    },
    data(){
       return {
             swiperOptions:{
                 pagination:'.swiper-pagination',
                 loop:true
             },
             show:false
       } 
    },
    computed:{
       showSwiper(){
           return this.list.length
       }
    }
}
</script>
<style lang="stylus" scoped>
.wrap>>>.swiper-pagination-bullet-active
 background:#fff!important
.wrap
  width:100%
  height:0
  padding-bottom:30.5%
  overflow:hidden
  .swiper-image
    width:100%  
 
</style>
