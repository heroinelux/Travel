<template>
	<div>
		<div class="title">周末去哪儿</div>
		<ul>
			<li class="item" v-for="item of recommendList" :key="item.id">
				<div class="item-img-wrapper">
					<img class="item-img" :src="item.imgUrl">
				</div>
				<div class="item-info">
					<p class="item-title">{{item.imgTitle}}</p>
					<p class="item-desc">{{item.imgDesc}}</p>
				</div>
			</li>
		</ul>
	</div>
</template>

<script>
	export default{
		name:"HomeWeekend",
		data:function(){
			return {
				recommendList:[{
					id:"0001",
					imgUrl:"http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg",
					imgTitle:"北京必游TOP10",
					imgDesc:"来北京必去的景点非这些地方莫属"
				},{
					id:"0002",
					imgUrl:"http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg",
					imgTitle:"北京必游TOP10",
					imgDesc:"来北京必去的景点非这些地方莫属"
				},{
					id:"0003",
					imgUrl:"http://img1.qunarzz.com/sight/source/1505/aa/7baaf8a851d221.jpg_r_640x214_1431200f.jpg",
					imgTitle:"北京必游TOP10",
					imgDesc:"来北京必去的景点非这些地方莫属"
				}],
			}	
		}
	}
</script>

<style lang="stylus" scoped>
@import "~@/assets/styles/varibles.styl"
	.title
		margin-top:.2rem
		background:#eee
		text-indent:.2rem
		line-height:.8rem
	.item
		margin-right:0
		overflow:hidden
		border-bottom:1px solid #eee
		.item-img-wrapper
			overflow:hidden
			height:0
			padding-bottom:37.09%
			.item-img	
				width:100%
		.item-info
			min-width:0
			padding:.2rem
			.item-title
				line-height:.54rem
				font-size:.32rem
				ellipsis()
			.item-desc
				line-height:.4rem
				color:#ccc
				ellipsis()
</style>