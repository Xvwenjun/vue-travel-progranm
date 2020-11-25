<template>
<div>
    <home-city></home-city>
    <search-city></search-city>
    <list-city :hot="hotCities"  :all="allCities"></list-city>
    <city-alphabet :all="allCities"></city-alphabet>
</div>
</template>
<script>
import HomeCity from './components/header'
import SearchCity from './components/search'
import ListCity from './components/list'
import CityAlphabet from './components/alphabet'
import axios from 'axios'
export default {
    name:"City",
    components:{
        HomeCity,
        SearchCity,
        ListCity,
        CityAlphabet
    },
    data(){
        return {
             hotCities:[],
             allCities:{}
        }
       
    },
    mounted(){
        this.getCityInfo()
    },
    methods:{
        getCityInfo(){
            axios.get('/api/city.json')
            .then(this.getCityInfoSucc)
        },
        getCityInfoSucc(res){
            res=res.data
            if(res.ret&&res.data){
                const data =res.data
                this.hotCities=data.hotCities
                this.allCities=data.cities
            }
        }
    }
}
</script>

<style lang="stylus" scoped>

</style>