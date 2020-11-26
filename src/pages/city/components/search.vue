<template>
<div class="search">
   <input class="search-input" 
          type="text" 
          placeholder="请输入城市名或拼音"
          v-model="keywords">
   <div ref="search" class="search-content" v-show="keywords">
      <ul>
         <li class="search-item border-bottom"
         v-for="item in list"
         :key="item.id"
         @click="cityChange(item.name)"
        >
        {{item.name}}</li>
         <li class="search-item border-bottom"
             v-show="hasnoCity">暂无匹配结果</li>
       </ul>
   </div>
</div>
</template>
<script> 
import Bscroll from 'better-scroll'
export default {
    name:"SearchCity",
    props:{
       cities:Object
    },
    data(){
       return {
          keywords:'',
          list:[],
          timer:null
       }
    },
      methods:{
         cityChange(city){
            this.$store.commit('cityChange',city)
            this.$router.push('/')
        }
      },
    computed:{
       hasnoCity(){
          return !this.list.length
       }
    },
    watch:{
       keywords() {
           if(this.timer){
              clearTimeout(this.timer)
           }
           if(!this.keywords){
              this.list=[]
              return
           }
           this.timer=setTimeout(()=>{
               const result=[]
               for(let i in this.cities){
                  this.cities[i].forEach(value => {
                     if(value.spell.indexOf(this.keywords) > -1 || value.name.indexOf(this.keywords) > -1){
                        result.push(value)
                     }
                  });
               }
               this.list=result
           },100)
           
       }
    },
    mounted(){
       this.scroll = new Bscroll(this.$refs.search)
    }

}
</script>

<style lang="stylus" scoped>
 @import '~styles/varibles.styl'
 .search
  height:.72rem
  background:$bgColor
  padding:0 .1rem
  .search-input
   box-sizing:border-box
   border-radius:.06rem
   text-align:center
   color:#666
   width:100%
   height:.62rem
   line-height:.62rem
   padding:0 .1rem
   text-align:center
  .search-content
   background:#eee
   position:absolute
   z-index:1
   overflow:hidden
   top:1.58rem
   left:0
   right:0
   bottom:0
   .search-item
    background:#fff
    line-height:.62rem
    padding-left:.2rem
    color:#666
    



</style>