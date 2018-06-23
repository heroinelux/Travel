<template>
	<div class="search">
		<input type="text" class="search-input" placeholder="输入城市名或拼音">
	</div>
</template>

<script>
	export default{
		name:"CitySerach"
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
</style>