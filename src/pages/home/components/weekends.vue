<template>
<div>
   <div class="title">周末去哪儿</div>
   <ul>
       <li class="item border-bottom " v-for="item of recommendList" :key="item.id">
            <div class="img-wrap">
             <img  class="item-img" :src="item.imgUrl">
            </div>
           <div class="item-info">
               <p class="item-name">{{item.name}}</p>
               <p class="item-desc">{{item.desc}}</p>
           </div>
       </li>
   </ul>
</div>
</template>

<script>
export default {
    name:'HomeWeekends',
    data(){
      return {
        recommendList:[
          {
            id:'0001',
            name:'含往返飞机票+4晚住宿',
            desc:'【跟团游】店长推荐🌞 下单立减!赠人鱼秀/旅拍＋海底餐厅+蜈支洲南山天涯+海边5日住',
            imgUrl:'https://imgs.qunarzz.com/p/p29/201302/28/3d20251a1b60350a93835fbb.jpg_256x160_e8f468b0.jpg'
          },
          {
            id:'0002',
            name:'含往返飞机票+4晚住宿',
            desc:'【跟团游】店长推荐🌞 下单立减!赠人鱼秀/旅拍＋海底餐厅+蜈支洲南山天涯+海边5日住',
            imgUrl:'https://imgs.qunarzz.com/p/p29/201302/28/3d20251a1b60350a93835fbb.jpg_256x160_e8f468b0.jpg'
          },
          {
            id:'0003',
            name:'含往返飞机票+4晚住宿',
            desc:'【跟团游】店长推荐🌞 下单立减!赠人鱼秀/旅拍＋海底餐厅+蜈支洲南山天涯+海边5日住',
            imgUrl:'https://imgs.qunarzz.com/p/p29/201302/28/3d20251a1b60350a93835fbb.jpg_256x160_e8f468b0.jpg'
          }
        ]        
      }
    }
}
</script>
<style lang="stylus" scoped>
@import '~styles/mixins.styl'
.title
 margin-top:.2rem
 line-height:.8rem
 background-color:#eee
 text-indent:.2rem
.img-wrap
 overflow:hidden
 height:0
 padding-bottom:37.09%
 .item-img
  width:100%
.item-info
 padding:.1rem
 .item-name 
  line-height:0.54rem
  font-size:.32rem
  ellipsis()
 .item-desc
  line-height:.4rem
  color:#ccc
  ellipsis()
</style>