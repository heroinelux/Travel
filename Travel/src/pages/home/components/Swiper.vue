<template>
    <div class="wrapper">
        <swiper :options="swiperOption">
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img class="swiper-img" :src="item.url">
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>
        </swiper>
    </div>
</template>

<script>
    export default{
        name:"HomeSwiper",
        data:function(){
            return {
                swiperOption:{
                    pagination:".swiper-pagination",
                    loop: true
                },
                swiperList:[{
                    id:"0001",
                    url:"http://img1.qunarzz.com/p/tts3/1805/3a/04facdb6da2bb102.jpg_r_390x260x90_89ac12f1.jpg"
                },{
                    id:"0002",
                    url:"https://imgs.qunarzz.com/p/tts7/1804/37/2e0cf65b49e68002.jpg_r_390x260x90_e65ce1b5.jpg"
                }]
            }
        }
        
    }
</script>

<style lang="stylus" scoped>
    .wrapper>>>.swiper-pagination-bullet-active
        background:red;
    .wrapper
        overflow: hidden
        width: 100%
        height:31.25vw
        background: #eee
    .swiper-img
        width: 100%
        height:31.25vw
</style>