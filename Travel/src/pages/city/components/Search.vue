<!-- 也可以更改 -->
<template>
	<div>
		<div class="search">
			<input type="text" class="search-input" placeholder="输入城市名或拼音" v-model="keyword">
		</div>
		<div class="search-content" v-show="keyword" ref="search">
			<ul>
				<li class="search-item" v-for="item of list" :key="item.id"
				@click="handleCityClick(item.name)">{{item.name}}
				</li>
				<li class="search-item" v-show="hasNoData">没有找到匹配数据</li>
			</ul>
		</div>
	</div>
</template>

<script>
	import Bscroll from "better-scroll"
	export default{
		name:"CitySearch",
		props:{
			cities:Object
		},
		data(){
			return{
				keyword:"",
				timer:null,
				list:[]
			}
		},
		methods:{
			handleCityClick(city){
				this.$store.commit("changeCity",city);
				this.$router.push("/");
			}
		},
		computed:{
			hasNoData(){
				return !this.list.length;
			}
		},
		watch:{
			keyword(){
				if(this.timer){
					clearTimeout(this.timer);
				}
				if(!this.keyword){
					this.list=[];
					return;
				}
				this.timer=setTimeout(()=>{
					const result=[];
					for(let i in this.cities){
						this.cities[i].forEach((value)=>{
							if(value.spell.search(this.keyword)!=-1||value.name.search(this.keyword)!=-1){
								result.push(value);
							}
						});
					}
					this.list=result;
				},100);
			}
		},
		mounted(){
			this.scroll=new Bscroll(this.$refs.search);
		}
	}
</script>

<style lang="stylus" scoped>
	@import "~@/assets/styles/varibles.styl"
	.search
		height:.72rem
		background:$bgColor
		padding:0 .1rem
		.search-input
			width:100%
			line-height:.62rem
			height:.62rem
			text-align:center
			border-radius:.06rem
			padding:0 .1rem
			box-sizing:border-box
			color:#666
	.search-content	
		background:#eee
		position:absolute
		top:1.58rem
		right:0
		bottom:0
		left:0
		overflow:hidden
		z-index:1
		.search-item
			line-height:.62rem
			padding-left:.2rem
			background:#fff
			color:#666
</style>