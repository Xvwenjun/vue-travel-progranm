<template>
<div>
    <home-city></home-city>
    <search-city :cities="allCities"></search-city>
    <list-city 
    :hot="hotCities" 
    :all="allCities"
    :letter="letter"></list-city>
    <city-alphabet 
    :all="allCities"
    @change="letterChange"></city-alphabet>
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
             allCities:{},
             letter:''
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
        },
        letterChange(letter){
            this.letter=letter
        }
    }
}
</script>

<style lang="stylus" scoped>

</style>