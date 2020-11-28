<template>
<ul class="item-list">
    <li class="item" 
    v-for="item of letters" 
    :key="item"
    :ref="item"
    @click="handleLetterChange"
    @touchstart.prevent="handletouchstart"
    @touchmove="handletouchmove"
    @touchend="handletouchend"
    >{{item}}</li>
</ul>
</template>
<script> 
export default {
    name:"CityAlphabet",
    props:{
        all:Object
    },
    data(){
        return{
            letterStatus:false,
            startY:0,
            timer:null
        }
    },
    updated(){
            this.startY=this.$refs['A'][0].offsetTop
    },
    methods:{
        handleLetterChange(e){
            this.$emit('change',e.target.innerText)
        },
        handletouchstart(){
           this.letterStatus=true
        },
        handletouchmove(e){
         if(this.letterStatus){
            if(this.timer){
                clearTimeout(this.timer)
            }
            this.timer=setTimeout(()=>{
            const touchY = e.touches[0].clientY-74
            const index = Math.floor( (touchY - this.startY) / 20)
                 if(index <= this.letters.length && index >= 0){
                this.$emit('change',this.letters[index])
                   }
                },15)
        
            }
        },
        handletouchend(){
           this.letterStatus=false

        }
    },
    computed:{
        letters(){
           const letters = []
           for(let i in this.all){
            letters.push(i)
           }
           return letters
        }
    }

}
</script>

<style lang="stylus" scoped>
 @import '~styles/varibles.styl'
 .item-list
  display:flex
  flex-direction:column
  justify-content:center
  position:absolute
  top:1.58rem
  right:0
  bottom:0
  width:.4rem
  .item
   line-height:.4rem
   text-align:center
   color:$bgColor
</style>