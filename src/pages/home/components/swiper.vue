<template>
<div class="wrap">
     <swiper :options="swiperOptions" >
       <swiper-slide v-for="item of swiperList" :key="item.id">
           <img class="swiper-image" alt="" :src="item.imgUrl">
        </swiper-slide>
       <div class="swiper-pagination" slot="pagination"></div>
   </swiper>
</div>
</template>
<script>
export default {
    name:"HomeSwiper",
    data(){
       return {
             swiperOptions:{
                 pagination:'.swiper-pagination',
                 loop:true
             },  
             swiperList:[
                 {
                     id:'0001',
                     imgUrl:"//imgs.qunarzz.com/vs_ceph_vcimg/569cae4ae98e9793f7341e85eed73c54.jpeg"
                 },{
                     id:"0002",
                     imgUrl:"//imgs.qunarzz.com/vs_ceph_vcimg/1cfbdaa2682ada2f854ea6114b3677c8.jpeg"
                 }
             ]     
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
  padding-bottom:31.25%
  overflow:hidden
  .swiper-image
    width:100%  
 
</style>
