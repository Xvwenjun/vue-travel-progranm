<template>
<div>
    <home-city></home-city>
    <search-city></search-city>
    <list-city></list-city>
    <city-alphabet></city-alphabet>
</div>
</template>
<script>
import HomeCity from './components/header'
import SearchCity from './components/search'
import ListCity from './components/list'
import CityAlphabet from './components/alphabet'
export default {
    name:"City",
    components:{
        HomeCity,
        SearchCity,
        ListCity,
        CityAlphabet
      
    }
}
</script>

<style lang="stylus" scoped>

</style>