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
                    url:"http://img1.qunarzz.com/piao/fusion/1806/fc/e47aa3e1c67bbc02.jpg_750x200_0f3eecf8.jpg"
                },{
                    id:"0002",
                    url:"http://img1.qunarzz.com/piao/fusion/1806/ab/4514055174ab3e02.jpg_750x200_274b2dd7.jpg"
                }]
            }
        }
        
    }
</script>

<style lang="stylus" scoped>
    .wrapper>>>.swiper-pagination-bullet-active
        background:#fff;
    .wrapper
        overflow: hidden
        width: 100%
        height:0
        padding-bottom:26.67%
        background: #eee
    .swiper-img
        width: 100%
</style>