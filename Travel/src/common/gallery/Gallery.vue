<template>
	<div class="container" @click="handleGalleryClick">
		<div class="wrapper">
			<swiper :options="swiperOption" v-if="show">
				<swiper-slide v-for="(item,index) of galleryImgs" :key="index">
					<img class="gallery-img" :src="item">
				</swiper-slide>
	            <div class="swiper-pagination"  slot="pagination"></div>
	        </swiper>
		</div>	
	</div>
</template>

<script>
	export default {
		name:"CommonGallery",
		props:{
			galleryImgs:Array
		},
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