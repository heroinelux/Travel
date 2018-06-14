<template>
	<div class="icons">
		<swiper :options="swiperOption">
			<swiper-slide v-for="(page,pageIndex) of pages" :key="pageIndex">
				<div class="icon" v-for="item of page" :key="item.id">
					<div class="icon-img"><img :src="item.imgUrl" :alt="item.desc"></div>
					<p class="icon-desc">{{item.desc}}</p>
				</div>
			</swiper-slide>		
		</swiper>
	</div>
</template>

<script>
	export default{
		name:"HomeIcons",
		props:{
			list:Array
		},
		data(){
			return {
				swiperOption:{
					autoplay:false
				}
			};
		},
		computed:{
			pages(){
				const pages=[];
				this.list.forEach((item,index)=>{
					const pageIndex=Math.floor(index/8);
					if(!pages[pageIndex]){
						pages[pageIndex]=[];
					}
					pages[pageIndex].push(item);
				});
				return pages;
			}
		}
	}
</script>

<style lang="stylus" scoped>
@import "~@/assets/styles/varibles.styl"
@import "~@/assets/styles/mixins.styl"
	.icons>>>.swiper-container{
		height:0
		padding-bottom:50%
	}
	.icons	
		margin-top:.1rem
		.icon	
			float:left
			width:25%
			height:0
			padding-bottom:25%
			overflow:hidden
			position:relative
			.icon-img
				position:absolute
				left:0
				top:0
				right:0
				bottom:.44rem
				padding-top:.1rem
				box-sizing:border-box
				img
					height:100%
					display:block
					margin:0 auto
			.icon-desc
				position:absolute
				width:100%
				bottom:0
				height:.44rem
				line-height:.44rem
				text-align:center
				color:$darkTextColor
				ellipsis()
</style>