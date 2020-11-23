<template>
 <div>
    <div>
        <home-header></home-header>
        <home-swiper></home-swiper>
        <home-icons></home-icons>
        <home-recommends></home-recommends>
        <home-weekends></home-weekends>
    </div>
  
 </div>
</template>

<script>
import HomeHeader from './components/Header'
import HomeSwiper from './components/Swiper'
import HomeIcons from './components/icons'
import HomeRecommends from './components/recommends'
import HomeWeekends from './components/weekends'

export default {
  name:"Home",
  components:{
      HomeHeader,
      HomeSwiper,
      HomeIcons,
      HomeRecommends,
      HomeWeekends
  }
}
</script>


<style>

</style>