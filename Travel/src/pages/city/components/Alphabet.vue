<template>
	<ul class="alphabet">
		<li 
			class="item"
			v-for="letter of letters" 
			:key="letter" 
			:ref="letter"
			@click="handleLetterClick"
			@touchstart="handleTouchStart"
			@touchmove="handleTouchMove"
			@touchend="handleTouchEnd"
			>{{letter}}</li>
	</ul>
</template>

<script>
	export default{
		name:"alphabet",
		props:{
			cities:Object
		},
		data(){
			return {
				touchStatus:false,
				startY:0,
				timer:null
			}
		},
		computed:{
			letters(){
				const letters=[];
				for(let key in this.cities){
					letters.push(key);
				}
				return letters;
			}
		},
		updated(){
			this.startY=this.$refs["A"][0].offsetTop;
		},
		methods:{
			handleLetterClick(event){
				this.$emit("change",event.target.innerHTML);
			},
			handleTouchStart(){
				this.touchStatus=true;
			},
			handleTouchMove(event){
				if(this.timer){
					clearTimeout(this.timer);
				}
				this.timer=setTimeout(()=>{
					if(this.touchStatus){
						const touchY=event.touches[0].clientY-74;
						const index=Math.floor((touchY-this.startY)/20);
						if(index>=0&&index<this.letters.length){
							this.$emit("change",this.letters[index]);
						}	
					}
				},16);
			},
			handleTouchEnd(){
				this.touchStatus=false;
			}
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