<template>
	<div class="alphabet">
		<div class="item">A</div>
		<div class="item">A</div>
		<div class="item">A</div>
		<div class="item">A</div>
		<div class="item">A</div>
		<div class="item">A</div>
		<div class="item">A</div>
		<div class="item">A</div>
		<div class="item">A</div>
		<div class="item">A</div>
	</div>
</template>

<script>
	export default{
		name:"alphabet"
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
		text-align:center
		line-height:.4rem
		color:$bgColor
		background:#fff
</style>