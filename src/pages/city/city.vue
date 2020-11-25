<template>
<div>
    <home-city></home-city>
    <search-city></search-city>
</div>
</template>
<script>
import HomeCity from './components/header'
import SearchCity from './components/search'
export default {
    name:"City",
    components:{
        HomeCity,
        SearchCity
    }
}
</script>

<style lang="stylus" scoped>

</style>