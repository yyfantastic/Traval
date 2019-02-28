<template>
    <div class="warpper">
        <swiper :options="swiperOption">
            <swiper-slide data-swiper-autoplay="3000" v-for='item of list' :key='item.id'>
                <img class='swiper-img' :src="item.imgUrl"/>
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
    export default {
        name: 'HomeSwiper',
        props:{
            list:Array
        },
        data() {
            return {
                swiperOption: {
                    pagination: '.swiper-pagination',
                    loop: true,
                    autoplay: true
                },
                swiperList: [
                    { id: '001', imgurl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/3921acb51460dc6fa9e3c7464fac5cbb.jpg_750x200_d992573a.jpg' },
                    { id: '002', imgurl: 'http://mp-piao-admincp.qunarzz.com/mp_piao_admin_mp_piao_admin/admin/20191/a5379fa4391437e3c111d17e59ed24d3.jpg_750x200_3126a045.jpg' }
                ]
            }
        }
    }
</script>
<style scoped>
    .warpper {
        width: 100%;
        height: 0;
        overflow: hidden;
        padding-bottom: 26.75%;
    }

    .swiper-img {
        width: 100%
    }

    .warpper>>>.swiper-pagination-bullet-active {
        background: white;
    }
   
    
    
</style>