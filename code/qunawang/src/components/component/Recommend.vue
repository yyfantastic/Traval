<template>
    <div>
        <div class="title">热销推荐</div>
        <ul>
            <router-link tag='li' class="item border-bottom" v-for='item in recommend' :key='item.id' :to='"/detail/"+item.id'>
                <img :src="item.imgUrl"
                    class="item-img">
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                    <button class="item-button">查看详情</button>
                </div>
            </router-link>
        </ul>
    </div>
</template>
<script>
    export default {
        name: 'HomeRecommend',
        props:['recommend'],
        data(){
            return{
                recommendList:[
                    {id:'001',imgurl:'http://img1.qunarzz.com/sight/p0/1701/7c/7c9c09560ca91808a3.img.jpg_200x200_749746ae.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'},
                    {id:'002',imgurl:'http://img1.qunarzz.com/sight/p0/1701/7c/7c9c09560ca91808a3.img.jpg_200x200_749746ae.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'},
                    {id:'003',imgurl:'http://img1.qunarzz.com/sight/p0/1701/7c/7c9c09560ca91808a3.img.jpg_200x200_749746ae.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'},
                    {id:'004',imgurl:'http://img1.qunarzz.com/sight/p0/1701/7c/7c9c09560ca91808a3.img.jpg_200x200_749746ae.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'},
                    {id:'005',imgurl:'http://img1.qunarzz.com/sight/p0/1701/7c/7c9c09560ca91808a3.img.jpg_200x200_749746ae.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'},
                    {id:'006',imgurl:'http://img1.qunarzz.com/sight/p0/1701/7c/7c9c09560ca91808a3.img.jpg_200x200_749746ae.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'}
                ]
            }
        }
    }
</script>
<style lang='stylus' scoped>
    @import '~@/assets/styles/mixins.styl'
    .title {
        line-height: .8rem;
        background: #eee;
        text-indent: .2rem;
        margin-top: .2rem;
    }

    .item {
        display: flex;
        height: 1.9rem;
        overflow: hidden;

    }

    .item-img {
        width: 1.7rem;
        height: 1.7rem;
        padding: .1rem
    }
    .item-info{
        flex: 1;
        padding: .1rem;
        min-width: 0;
    }
    .item-title{
        line-height: .54rem;
        font-size: .32rem
        ellipsis()
    }
    .item-desc{
        line-height: .4rem;
        color: #ccc
        ellipsis()
    }
    .item-button{
        background: #ff9300;
        padding: 0 .2rem;
        border-radius: .06rem;
        margin-top: .16rem;
        color: #fff;
        line-height: .44rem
    }
</style>