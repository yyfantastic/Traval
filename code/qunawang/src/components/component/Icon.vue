<template>
    <div class="icons">
        <swiper :options="swiperOption">
            <swiper-slide v-for='(page,index) in pages' :key='index'>
                <div class="icon"  v-for='item in page' :key='item.id'>
                    <div class="icon-img"><img class='iconimg-content'
                            :src="item.imgUrl"></div>
                    <p class="icon-desc">{{item.desc}}</p>
                </div>
            </swiper-slide>
        </swiper>
    </div>
</template>
<script>
    export default {
        name: 'HomeIcon',
        props:['icon'],
        data(){
            return {
                iconList:[
                    {id:'001',imgurl:'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png'},
                    {id:'002',imgurl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png'},
                    {id:'003',imgurl:'http://img1.qunarzz.com/piao/fusion/1804/5a/13ceb38dcf262f02.png'},
                    {id:'004',imgurl:'http://img1.qunarzz.com/piao/fusion/1901/16/caa09d30b24d8302.png'},
                    {id:'005',imgurl:'http://img1.qunarzz.com/piao/fusion/1901/16/caa09d30b24d8302.png'},
                    {id:'006',imgurl:'http://img1.qunarzz.com/piao/fusion/1901/16/caa09d30b24d8302.png'},
                    {id:'007',imgurl:'http://img1.qunarzz.com/piao/fusion/1901/16/caa09d30b24d8302.png'},
                    {id:'008',imgurl:'http://img1.qunarzz.com/piao/fusion/1901/16/caa09d30b24d8302.png'},
                    {id:'009',imgurl:'http://img1.qunarzz.com/piao/fusion/1901/16/caa09d30b24d8302.png'}
                ],
                swiperOption:{
                    autoplay:false
                }
            }
        },computed:{
            pages (){
                const pages=[]
                this.icon.forEach((item,index)=>{
                    const page=Math.floor(index/8)
                    if(!pages[page]){
                        pages[page]=[]
                    }
                    pages[page].push(item)
                })
                return pages
            }
        }
    }
</script>
<style lang="stylus" scoped>
    @import "~@/assets/styles/varibles.styl"
    @import "~@/assets/styles/mixins.styl"
    .icons>>>.swiper-container {
        height: 0;
        padding-bottom: 50%;
        
    }
    .icons{
        margin-top: .1rem;
    }
    .icon {
        width: 25%;
        float: left;
        padding-bottom: 25%;
        height: 0;
        overflow: hidden;
        position: relative;
    }

    .icon-img {
        position: absolute;
        top: 0;
        left: 0;
        right: 0;
        bottom: .44rem;
        box-sizing: border-box;
        padding: .1rem
    }

    .iconimg-content {
        height: 100%;
        display: block;
        margin: 0 auto
    }

    .icon-desc {
        position: absolute;
        bottom: 0;
        left: 0;
        right: 0;
        line-height: .44rem;
        height: .44rem;
        color: darkcolor;
        text-align: center;
        ellipsis()
    }
</style>