<template>
    <div class="container">
        <div class="wrapper">
            <swiper :options="swiperOption">
                <swiper-slide>
                    <img class='gallary-img'
                        src="http://img1.qunarzz.com/sight/p0/1701/7c/7c9c09560ca91808a3.img.jpg_r_800x800_d356f9db.jpg" />
                </swiper-slide>
                <swiper-slide>
                    <img class='gallary-img'
                        src="http://img1.qunarzz.com/sight/p0/1701/7c/7c9c09560ca91808a3.img.jpg_r_800x800_d356f9db.jpg" />
                </swiper-slide>
                <swiper-slide>
                    <img class='gallary-img'
                        src="http://img1.qunarzz.com/sight/p0/1701/7c/7c9c09560ca91808a3.img.jpg_r_800x800_d356f9db.jpg" />
                </swiper-slide>
                <swiper-slide>
                    <img class='gallary-img'
                        src="http://img1.qunarzz.com/sight/p0/1701/7c/7c9c09560ca91808a3.img.jpg_r_800x800_d356f9db.jpg" />
                </swiper-slide>
                <!-- <div class="swiper-pagination" slot="pagination"></div> -->
            </swiper>
        </div>
    </div>
</template>
<script>
    export default {
        name: 'CommonGallary'
    }
</script>
<style scoped>
    .container {
        display: flex;
        flex-direction: column;
        justify-content: center;
        position: fixed;
        background: #000;
        top: 0;
        left: 0;
        bottom: 0;
        right: 0;
        z-index: 99;
    }

    .wrapper {
        width: 100%;
        height: 0;
        overflow: hidden;
        padding-bottom: 100%;
    }

    .gallary-img {
        width: 100%
    }
</style>