<template>
	<div>
		<ul class="alphabet-wrap">
			<li class="alphabet-wrap-list" v-for="item of letters" :key="item">{{item}}</li>
		</ul>
	</div>	
</template>

<script>
	export default {
		name : "CityAlphabet",
		props:{
			cities:Object
		},
		computed : {
			 letters () {
			 	const letters = [] 
			 	for(let key in this.cities){
			 		letters.push(key)
			 	}
			 	return letters
			 	console.log(letters)
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
  width:.4rem
  .alphabet-wrap-list
    line-height:.4rem
    text-align:center
    color:$bgColor	
</style>