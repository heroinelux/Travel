<template>
	<div>
		<div class="banner" @click="handleBannerClick">
			<img class="banner-img" src="http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg" alt="banner-img">
			<div class="banner-info">
				<div class="banner-title">大连圣亚海洋世界(AAAA景区)</div>
				<div class="banner-number">
					<span class="iconfont banner-icon">&#xe600;</span>
					39
				</div>
			</div>
		</div>
		<common-gallery v-show="showGallery"  @close="handleClose"></common-gallery>
	</div>
	
</template>

<script>
	import CommonGallery from "@/common/gallery/Gallery"
	export default{
		name:"DetailBanner",
		data(){
			return {
				showGallery:false
			}
		},
		components:{
			CommonGallery,
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