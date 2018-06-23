<template>
	<ul class="alphabet">
		<li v-for="(item,key) of cities" :key="key" class="item">{{key}}</li>
	</ul>
</template>

<script>
	export default{
		name:"alphabet",
		props:{
			cities:Object
		}
	}
</script>


<style lang="stylus" scoped>
@import "~@/assets/styles/varibles.styl"
.alphabet
	display:flex
	flex-direction:column
	justify-content:center
	position:absolute
	top:1.58rem
	right:0
	bottom:0
	width:.4rem
	.item
		list-style:none
		text-align:center
		line-height:.4rem
		color:$bgColor
		background:#fff
</style>