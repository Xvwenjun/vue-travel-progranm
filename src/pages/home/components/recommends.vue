<template>
<div>
   <div class="title">热销推荐</div>
   <ul>
       <li class="item border-bottom " v-for="item of recommendList" :key="item.id">
             <img  class="item-img" :src="item.imgUrl">
           <div class="item-info">
               <p class="item-name">{{item.name}}</p>
               <p class="item-desc">{{item.desc}}</p>
               <button class="item-more">查看详情</button>
           </div>
       </li>
   </ul>
</div>
</template>

<script>
export default {
    name:'HomeRecommends',
    data(){
      return {
        recommendList:[
          {
            id:'0001',
            name:'含往返飞机票+4晚住宿',
            desc:'【跟团游】店长推荐🌞 下单立减!赠人鱼秀/旅拍＋海底餐厅+蜈支洲南山天涯+海边5日住',
            imgUrl:'https://imgs.qunarzz.com/p/p70/1809/e7/4941057a6aae702.jpg_256x160_9fee6ccb.jpg'
          },
          {
            id:'0002',
            name:'含往返飞机票+4晚住宿',
            desc:'【跟团游】店长推荐🌞 下单立减!赠人鱼秀/旅拍＋海底餐厅+蜈支洲南山天涯+海边5日住',
            imgUrl:'https://imgs.qunarzz.com/p/p70/1809/e7/4941057a6aae702.jpg_256x160_9fee6ccb.jpg'
          },
          {
            id:'0003',
            name:'含往返飞机票+4晚住宿',
            desc:'【跟团游】店长推荐🌞 下单立减!赠人鱼秀/旅拍＋海底餐厅+蜈支洲南山天涯+海边5日住',
            imgUrl:'https://imgs.qunarzz.com/p/p70/1809/e7/4941057a6aae702.jpg_256x160_9fee6ccb.jpg'
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
.item 
  overflow:hidden
  display:flex
  height:1.9rem
  .item-img
   width:1.7rem
   height:1.7rem
   padding:.1rem
  .item-info
   flex:1
   padding:.1rem
   min-width:0
   .item-name 
    height:0.54rem
    font-size:.32rem
    ellipsis()
   .item-desc
    line-height:.4rem
    color:#ccc
    ellipsis()
   .item-more
    line-height:.44rem
    margin-top:.16rem
    background-color:#ff9300
    padding:0 .2rem
    border-radius:.06rem
    color:#fff
</style>