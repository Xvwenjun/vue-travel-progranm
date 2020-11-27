<template>
    <div>
        <banner-detail 
        :sightName="sightName"
        :bannerImg="bannerImg"
        :gallaryImgs="gallaryImgs"
        ></banner-detail>
        <detail-header></detail-header>
        <div class="content">
             <detail-list  :list="list"></detail-list>
        </div>
       
    </div>
</template>
<script>
import BannerDetail from './components/banner'
import DetailHeader from './components/header'
import DetailList from './components/list'
import axios from 'axios'
export default {
    name:'Detail',
    components:{
       BannerDetail,
       DetailHeader,
       DetailList
    },
    data(){
        return{
             list:[],
             sightName: '',
             bannerImg: '',
             gallaryImgs: [],
        }
    },
    methods:{
        getDetailInfo(){
            axios.get('/api/detail.json',{
                params:{
                    id:this.$route.params.id
                }
            }).then(this.getDetailInfoSucc)
        },
        getDetailInfoSucc(res){
           res=res.data
          if(res.ret&&res.data){
              const data=res.data
              this.sightName=data.sightName
              this.bannerImg=data.bannerImg
              this.gallaryImgs=data.gallaryImgs
              this.list=data.categoryList
              
          }
        }
    },
    mounted(){
        this.getDetailInfo()
    }
}
</script>

<style lang="stylus" scoped>
.content
 height:20rem
</style>