<template>
	<div class="list" ref="wrapper">
		<div class="list-inner">
			<div class="area">
				<div class="title">当前城市</div>
				<div class="content">
					<div class="btn-wrapper"><div class="btn">{{this.currentCity}}</div></div>
				</div>
			</div>
			<div class="area">
				<div class="title">热门城市</div>
				<div class="content">
					<div 
						class="btn-wrapper" 
						v-for="(item,index) of hot" 
						:key="item.id"
						@click="handleCityClick(item.name)"
					>
						<div class="btn">{{item.name}}</div>
					</div>
				</div>
			</div>
			<div class="area" v-for="(item,key) of cities" :key="key" :ref="key">
				<div class="title">{{key}}</div>
				<div class="item-list">
					<div class="item" v-for="innerItem of item"  @click="handleCityClick(innerItem.name)">{{innerItem.name}}</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script>
	import {mapState,mapMutations} from "vuex"
	import BScroll from "better-scroll"
	export default{
		name:"CityList",
		props:{
			cities:Object,
			hot:Array,
			letter:String
		},
		computed:{
			...mapState({
				currentCity:"city"
			})
		},
		methods:{
			handleCityClick(city){
				// this.$store.commit("changeCity",city);
				this.changeCity(city);
				this.$router.push("./");
			},
			...mapMutations(["changeCity"])
		},
		mounted(){
			this.scroll=new BScroll(this.$refs.wrapper);
		},
		watch:{
			letter(){
				if(this.letter){
					const element=this.$refs[this.letter][0]
					this.scroll.scrollToElement(element);
				}
			}
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