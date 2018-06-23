<template>
	<div class="list" ref="wrapper">
		<div class="list-inner">
			<div class="area">
				<div class="title">热门城市</div>
				<div class="content">
					<div class="btn-wrapper"><div class="btn">北京</div></div>
				</div>
			</div>
			<div class="area">
				<div class="title">热门城市</div>
				<div class="content">
					<div class="btn-wrapper"><div class="btn">北京</div></div>
					<div class="btn-wrapper"><div class="btn">北京</div></div>
					<div class="btn-wrapper"><div class="btn">北京</div></div>
					<div class="btn-wrapper"><div class="btn">北京</div></div>
					<div class="btn-wrapper"><div class="btn">北京</div></div>
					<div class="btn-wrapper"><div class="btn">北京</div></div>
					<div class="btn-wrapper"><div class="btn">北京</div></div>
				</div>
			</div>
			<div class="area">
				<div class="title">A</div>
				<div class="item-list">
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
				</div>
			</div>
			<div class="area">
				<div class="title">A</div>
				<div class="item-list">
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
				</div>
			</div>
			<div class="area">
				<div class="title">A</div>
				<div class="item-list">
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
					<div class="item">lanqi</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import BScroll from "better-scroll"
	export default{
		name:"CityList",
		mounted(){
			this.scroll=new BScroll(this.$refs.wrapper);
		}
	}
</script>

<style lang="stylus" scoped>
.list
	position:absolute
	top:1.58rem
	right:0
	bottom:0
	left:0
	overflow:hidden
	.title
		line-height:.54rem
		padding-left:.2rem
		border-top:1px solid #ccc
		border-bottom:1px solid #ccc
		background:#eee
		font-size:.26rem
		color:#666
	.content
		padding:.1rem .6rem .1rem .1rem
		overflow:hidden
		.btn-wrapper
			width:33.3%
			float:left
			.btn
				text-align:center
				margin:.1rem
				padding:.1rem 0
				border:.02rem solid #ccc
				border-radius:.06rem
	.item-list
		.item
			line-height:.76rem
			padding-left:.2rem
			border-bottom:.02rem solid #ccc
			
			
			
</style>