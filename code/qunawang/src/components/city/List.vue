<template>
    <div class="list" ref='wrapper'>
        <div>
            <div class="area">
                <div class="title border-topbottom">当前城市</div>
                <div class="buttonlist">
                    <div class="buttonwraper">
                        <div class="button">{{this.city}}</div>
                    </div>
                </div>
            </div>
            <div class="area">
                <div class="title border-topbottom">热门城市</div>
                <div class="buttonlist">
                    <div class="buttonwraper" v-for='item in hotCities' :key='item.id' @click='handlecityclick(item.name)'>
                        <div class="button">{{item.name}}</div>
                    </div>
                </div>
            </div>
            <div class="area" v-for='(item,key) in cities' :key='key' :ref='key'>
                <div class="title border-topbottom">{{key}}</div>
                <div class="itemlist">
                    <div class="item border-bottom" v-for='innerite in item' :key='innerite.id' @click='handlecityclick(innerite.name)'>
                        {{innerite.name}}
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>
<script>
    import Bscroll from 'better-scroll'
    import {mapState,mapMutations} from 'vuex'
    export default {
        name: "CityList",
        computed:{
            ...mapState(['city'])
        },
        props: ['hotCities', 'cities','letter'],
        mounted() {
            this.scroll = new Bscroll(this.$refs.wrapper)
        },
        watch:{
            letter(){
                if(this.letter){
                    const element=this.$refs[this.letter][0]
                    this.scroll.scrollToElement(element)
                }
            }
        },
        methods:{
            handlecityclick(city){
                this.changecity(city)
                this.$router.push("/")
            },
            ...mapMutations(['changecity'])
        }
    }
</script>
<style lang='stylus' scoped>
    @import '~@/assets/styles/varibles.styl'

    .title {
        line-height: .54rem;
        background: #eee;
        padding-left: .2rem;
        color: #666;
        font-size: .26rem;
        border-color: #777
    }

    .border-topbottom {
        border-color: #777
    }

    .buttonlist {
        padding: .1rem .1rem;
        overflow: hidden;
        padding: .1rem .6rem .1rem .1rem
    }

    .buttonwraper {
        width: 33.33%;
        float: left;
    }

    .button {
        text-align: center;
        margin: .1rem .1rem;
        border: .02rem solid #ccc;
        padding: .1rem 0;
        border-radius: .06rem
    }

    .itemlist .item {
        line-height: .76rem;
        color: #666;
        padding-left: .2rem;
        border-bottom: 1px solid #ccc;
    }

    .list {
        overflow: hidden;
        position: absolute;
        top: 1.59rem;
        left: 0;
        right: 0;
        bottom: 0;
    }
</style>