<template>
    <div>
        <banner-detail></banner-detail>
        <detail-header></detail-header>
    </div>
</template>
<script>
import BannerDetail from './components/banner'
import DetailHeader from './components/header'
export default {
    name:'Detail',
    components:{
       BannerDetail,
       DetailHeader
    }
}
</script>

<style lang="stylus" scoped>

</style>