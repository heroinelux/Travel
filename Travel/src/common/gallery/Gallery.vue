<template>
	<div class="container" @click="handleGalleryClick">
		<div class="wrapper">
			<swiper :options="swiperOption" v-if="show">
	            <swiper-slide>
	                <img class="gallery-img" src="http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_800x800_70debc93.jpg">
	            </swiper-slide>
	            <swiper-slide>
	                <img class="gallery-img" src="http://img1.qunarzz.com/sight/p0/1709/76/7691528bc7d7ad3ca3.img.png_800x800_9ef05ee7.png">
	            </swiper-slide>
	            <div class="swiper-pagination"  slot="pagination"></div>
	        </swiper>
		</div>	
	</div>
</template>

<script>
	export default {
		name:"CommonGallery",
		data(){
			return {
				show:true,
				swiperOption:{
                    pagination:".swiper-pagination",
                    paginationType:"fraction",
                   	observer:true,
    				observeParents:true,
                }
			}
		},
		methods:{
			handleGalleryClick(){
				this.$emit("close");
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.container >>> .swiper-container
		overflow:inherit
	.container
		display:flex
		flex-direction:column
		justify-content:center
		position:fixed
		z-index:10
		top:0
		right:0
		bottom:0
		left:0
		background:#000
		color:#fff
		.wrapper
			height:0
			width:100%
			padding-bottom:100%
			.gallery-img
				width:100%
			.swiper-pagination
				color:#fff
				bottom:-1rem
				z-index:100
</style>