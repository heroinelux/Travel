<template>
	<div>
		<div class="banner" @click="handleBannerClick">
			<img class="banner-img" :src="bannerImg" alt="banner-img">
			<div class="banner-info">
				<div class="banner-title">{{sightName}}</div>
				<div class="banner-number">
					<span class="iconfont banner-icon">&#xe600;</span>
					{{galleryImgs.length}}
				</div>
			</div>
		</div>
		<fade>
			<common-gallery :galleryImgs="galleryImgs" v-show="showGallery"  @close="handleClose"></common-gallery>
		</fade>
		
	</div>
	
</template>

<script>
	import CommonGallery from "@/common/gallery/Gallery"
	import Fade from "@/common/fade/Fade"
	export default{
		name:"DetailBanner",
		props:{
			sightName:String,
			bannerImg:String,
			galleryImgs:Array
		},
		data(){
			return {
				showGallery:false
			}
		},
		components:{
			CommonGallery,
			Fade
		},
		methods:{
			handleBannerClick(){
				this.showGallery=true;
			},
			handleClose(){
				this.showGallery=false;
			}
		}
	}
</script>

<style lang="stylus" scoped>
	.banner
		height:0
		padding-bottom:55%
		overflow:hidden
		position:relative
		.banner-img
			width:100%
		.banner-info
			position:absolute
			bottom:0
			left:0
			right:0
			display:flex
			color:#fff
			line-height:.6rem
			background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0,.8));
			.banner-title
				flex:1
				font-size:.32rem
				padding:0 .2rem
			.banner-number
				padding:0 .4rem
				height:.32rem
				line-height:.32rem
				margin-top:.14rem
				border-radius:.2rem
				background:rgba(0,0,0,.8)
				font-size:.24rem
				.banner-icon
					font-size:.24rem
</style>