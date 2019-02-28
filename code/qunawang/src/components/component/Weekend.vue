<template>
    <div>
        <div class="title">周末去哪儿</div>
        <ul>
            <li class="item border-bottom" v-for='item in weekend' :key='item.id'>
                <div class="item-img-warpper">
                    <img :src="item.imgUrl" class="item-img">
                </div>
                <div class="item-info">
                    <p class="item-title">{{item.title}}</p>
                    <p class="item-desc">{{item.desc}}</p>
                </div>
            </li>
        </ul>
    </div>
</template>
<script>
    export default {
        name: 'HomeWeekend',
        props:['weekend'],
        data(){
            return{
                recommendList:[
                    {id:'001',imgurl:'http://img1.qunarzz.com/sight/source/1511/6d/1cf99c1a1ee96d.jpg_r_640x214_c720177b.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'},
                    {id:'002',imgurl:'http://img1.qunarzz.com/sight/source/1511/6d/1cf99c1a1ee96d.jpg_r_640x214_c720177b.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'},
                    {id:'003',imgurl:'http://img1.qunarzz.com/sight/source/1511/6d/1cf99c1a1ee96d.jpg_r_640x214_c720177b.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'},
                    {id:'004',imgurl:'http://img1.qunarzz.com/sight/source/1511/6d/1cf99c1a1ee96d.jpg_r_640x214_c720177b.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'},
                    {id:'005',imgurl:'http://img1.qunarzz.com/sight/source/1511/6d/1cf99c1a1ee96d.jpg_r_640x214_c720177b.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'},
                    {id:'006',imgurl:'http://img1.qunarzz.com/sight/source/1511/6d/1cf99c1a1ee96d.jpg_r_640x214_c720177b.jpg',title:'大连圣亚海洋世界',desc:'浪漫大连首站，浪漫的海洋主题公园'}
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
    .item-img-warpper{
        overflow: hidden;
        height: 0;
        padding-bottom: 33.9%;
    }
    .item.info{
        padding: .1rem;
    }
    .item-img {
       width: 100%
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
</style>