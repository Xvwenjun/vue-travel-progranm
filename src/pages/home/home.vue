<template>
 <div>
    <div>
        <home-header ></home-header>
        <home-swiper :list="swiperList"></home-swiper>
        <home-icons :list="iconsList"></home-icons>
        <home-recommends :list="recommendList"></home-recommends>
        <home-weekends :list="weekendsList"></home-weekends>
    </div>
  
 </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icons'
import HomeRecommends from './components/recommends'
import HomeWeekends from './components/weekends'
import axios from 'axios'

export default {
  name:"Home",
  components:{
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeRecommends,
      HomeWeekends
  },
  data(){
    return {
        swiperList:[],
        iconsList:[],
        recommendList:[],
        weekendsList:[]
      }
    
  },
  mounted(){
  this.getHomeInfo()
  },
  methods:{
    getHomeInfo(){
      axios.get('/api/index.json')
      .then(this.getHomeInfoSucc)
    },
    getHomeInfoSucc(res){
      res= res.data
      if(res.ret&&res.data){
        const data = res.data
        this.swiperList=data.swiperList
        this.iconsList=data.iconList
        this.weekendsList=data.weekendList
        this.recommendList=data.recommendList
      }
  }
  }
}
</script>


<style>

</style>