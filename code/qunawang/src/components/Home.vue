<template>
    <div>
        <home-header/>
        <home-swiper :list='swiperList'/>
        <HomeIcon :icon='iconList'/>
        <HomeRecommend :recommend='recommendList'/>
        <HomeWeekend :weekend='weekendList'/>
    </div>
</template>
<script>
    import HomeHeader from './component/Header'
    import HomeSwiper from './component/Swiper'
    import HomeIcon from './component/Icon'
    import HomeRecommend from './component/Recommend'
    import HomeWeekend from './component/Weekend'
    import axios from 'axios'
    import {mapState} from 'vuex'
    export default{
        name:'Home',
        data(){
            return{
                lastcity:'',
                swiperList:[],
                iconList:[],
                recommendList:[],
                weekendList:[]
            }
        },
        components:{
            HomeHeader,
            HomeSwiper,
            HomeIcon,
            HomeRecommend,
            HomeWeekend
        },
        computed:{
            ...mapState(['city'])
        },
        methods:{
            getHomeinfo(){
                axios.get("/api/index.json?city=" + this.city).then(this.getHomeinfosucc)
            },
            getHomeinfosucc(res){
                console.log(res)
                res=res.data;
                if(res.ret&&res.data){ 
                    const data=res.data
                    this.swiperList=data.swiperList
                    this.iconList=data.iconList
                    this.recommendList=data.recommendList
                    this.weekendList=data.weekendList
                }
            }
        },
        mounted(){
            this.lastcity=this.city
            this.getHomeinfo()
        },
        activated(){
            if(this.lastcity!==this.city){
                this.lastcity=this.city
                this.getHomeinfo()
            }
        }
        
    }
</script>