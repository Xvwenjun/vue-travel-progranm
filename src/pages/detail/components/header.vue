<template>
<div>
    <router-link tag="div" class="header-abs" to="/" v-show="showAbs">
        <div class="iconfont header-abs-back-icon">&#xe624;</div>
    </router-link>
    <div class="header-fix" :style="styleOpacity"  v-show="!showAbs"  > 
        <router-link to="/">    
            <div class="iconfont header-fix-back-icon">&#xe624;</div>
        </router-link>
        景点详情
    </div>
    <div class="hig">
    </div>
</div>  
</template>
<script>
export default {
    name:'DetailHeader',
    data(){
        return {
            showAbs:true,
            styleOpacity:{
                opacity:0
            }
        }
    },
    methods:{
        handleScroll(){
            const top = document.documentElement.scrollTop
            if(top>60){
                let opacity = top / 140
                opacity= opacity > 1 ? 1 : opacity
                this.styleOpacity={opacity}
                this.showAbs=false
            }else{
                 this.showAbs=true
            }
        }
    },
    mounted(){
        window.addEventListener('scroll',this.handleScroll)
    },
    unmounted(){
        window.removeEventListener(this.handleScroll)
    }
    
}
</script>

<style lang="stylus" scoped>
 @import '~styles/varibles.styl'
 .header-abs
  position:absolute
  height: .8rem
  width:.8rem
  left:.2rem
  top:.2rem
  line-height:.8rem
  border-radius:.4rem
  text-align:center
  background:rgba(0,0,0,.8)
  .header-abs-back-icon
   color:#fff
   font-size:.4rem
 .header-fix
  position:fixed
  top:0
  left:0
  right:0
  height:$headerHeight
  line-height:$headerHeight
  text-align:center
  background:$bgColor
  font-size:.32rem
  color:#fff
  .header-fix-back-icon
   position:absolute
   top:0
   left:0
   width:.64rem
   text-align:center
   font-size:.4rem
   color:#fff
 .hig
   height:100rem
   background:pink
</style>