<template>
	<div class="header">
		<router-link to="/" tag="div" class="header-abs" v-show="showAbs">
			<div class="iconfont header-abs-back">&#xe65b;</div>
		</router-link>		
		<div class="header-fixed" v-show="!showAbs" :style="opacityStyle">
			<router-link to="/" tag="div" class="iconfont header-fixed-back">&#xe65b;</router-link>
			<div class="header-fixed-title">景点详情</div>
		</div>
	</div>
</template>

<script>
	export default{
		name:"DetailHeader",
		data(){
			return {
				showAbs:true,
				opacityStyle:{
					opacity:0
				}
			}
		},
		methods:{
			handleScroll(){
				let top=document.documentElement.scrollTop||document.body.scrollTop;
				if(top>60){
					let opacity=top/140;
					opacity=(opacity>1)?1:opacity;
					this.opacityStyle.opacity=opacity;
					this.showAbs=false;
				}else{
					this.showAbs=true;
				}
			}
		},
		mounted(){
			window.addEventListener("scroll",this.handleScroll);
		},
		unmounted(){
			window.removeEventListener("scroll",this.handleScroll);
		}
	}
</script>

<style lang="stylus" scoped>
@import "~@/assets/styles/varibles.styl"
	.header-abs
		position:absolute
		top:.2rem
		left:.2rem
		width:.8rem
		height:.8rem
		line-height:.8rem
		border-radius:50%
		text-align:center
		background:rgba(0,0,0,.8)
		.header-abs-back
			color:#fff
			font-size:.4rem
	.header-fixed
		z-index:2
		position:fixed 
		top:0
		left:0
		right:0
		background:$bgColor
		color:#fff
		line-height:$headerHeight
		height:$headerHeight
		text-align:center
		font-size:.32rem
		display:flex
		.header-fixed-back
			postion:absolute
			top:0
			left:0
			width:.64rem
			text-align:center
			font-size:.4rem
			color:#fff
		.header-fixed-title
			flex:1
			margin-right:.64rem
</style>