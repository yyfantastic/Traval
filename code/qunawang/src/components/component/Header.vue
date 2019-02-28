<template>
    <div class="header">
        <div class="header-left back-icon"><div class="iconfont">&#xe624;</div></div>
        <div class="header-input"><span class="iconfont">&#xe632;</span>输入城市／景点／游玩主题</div>
        <router-link to='/city'><div class="header-right">{{this.city}}<span class="iconfont arror-icon">&#xe64a;</span></div></router-link>
    </div>
</template>
<script>
    import {mapState} from 'vuex'
    export default {
        name: 'HomeHeader',
        computed:{
            ...mapState(['city'])
        }
    }
</script>
<style lang='stylus' scoped>
    @import '~@/assets/styles/varibles.styl'
   .header{
       display: flex;
       line-height: .86rem;
       background:bgcolor;
       color: #fff
   }
   .header-left{
       width:.64rem;
       float: left;
   }
   .back-icon{
       text-align: center;
       font-size: .4rem
   }
   .header-input{
       flex: 1;
       background: #fff;
       border-radius: .1rem;
       margin-top: .12rem;
       line-height: .64rem;
       height: .64rem;
       margin-left: .2rem;
       color:#ccc;
       padding-left: .2rem;
   }
   .header-right{
       min-width: 1.04rem;
       float: right;
       text-align: center;
       color:white;
       padding: 0 .1rem
   }
   .arror-icon{
       font-size: .24rem;
       margin-left: -.04rem;
   }
</style>