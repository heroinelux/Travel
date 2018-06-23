<template>
	<div>
		<city-header></city-header>
		<city-search></city-search>
		<city-list :cities="cities" :hot="hotCities"></city-list>
		<city-alphabet :cities="cities"></city-alphabet>
	</div>
</template>

<script>
	import CityHeader from "./components/Header"
	import CitySearch from "./components/Search"
	import CityList from "./components/List"
	import CityAlphabet from "./components/Alphabet"
	import axios from "axios"
	export default{
		name:"City",
		components:{
			CityHeader,
			CitySearch,
			CityList,
			CityAlphabet
		},
		data:function(){
			return{
				cities:{},
				hotCities:[]
			}
		},
		methods:{
			getCityInfo(){
				axios.get("/static/mock/city.json")
					 .then(this.getCityInfoSucc);
			},
			getCityInfoSucc(res){
				res=res.data;
				if(res.ret===true&&res.data){
					const data=res.data;
					this.cities=data.cities;
					this.hotCities=data.hotCities;
				}
			}
		},
		mounted(){
			this.getCityInfo();
		}
	}
</script>

<style>
	
</style>