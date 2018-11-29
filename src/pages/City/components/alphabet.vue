<template>
	<div>
		<ul class="alphabet-wrap">
			<li class="alphabet-wrap-list" 
				v-for="item of letters" 
				:key="item"
				:ref="item"
				@click = "handleClick"
				@touchstart = 'handleTouchStart'
				@touchmove = 'handleTouchMove'
				@touchend = 'handleTouchEnd'
			>
				{{item}}
			</li>
		</ul>
	</div>	
</template>

<script>
	export default {
		name : "CityAlphabet",
		props:{
			cities:Object
		},
		data () {
			return {
				touchStart:false,
				startY:0,
				timer:null
			}
		},
		update () {
			startY = this.$refs['A'][0].offsetTop
		},
		computed : {
			 letters () {
			 	const letters = [] 
			 	for(let key in this.cities){
			 		letters.push(key)
			 	}
			 	return letters
			 }
		},
		methods:{
			handleClick (e) {
				 this.$emit("changeLetters",e.target.innerText)
			},
			handleTouchStart () {
				this.touchStart = true
			},
			handleTouchMove (e) {
			  if(this.touchStart){
			  	if(this.timer){
			  		clearTimeout(this.timer)
			  	}
			  	this.timer = setTimeout(()=>{
			  		const touchY = e.touches[0].clientY -79;
				    const index = Math.floor((touchY-this.startY)/20);
				    if(index >=0 && index<= this.letters.length){
				       this.$emit('changeLetters',this.letters[index])
				    }	
			  	},16)
			  }
			},
			handleTouchEnd () {
				this.touchStart = false
			}
	  }
}	
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.alphabet-wrap
  display:flex
  flex-direction:column
  justify-content:center
  position:absolute
  right:0
  bottom:0
  top:1.58rem
  width:.6rem
  .alphabet-wrap-list
    line-height:.4rem
    text-align:center
    color:$bgColor	
</style>