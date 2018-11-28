<template>
	<div>
		<ul class="alphabet-wrap">
			<li class="alphabet-wrap-list">A</li>
			<li class="alphabet-wrap-list">A</li>
			<li class="alphabet-wrap-list">A</li>
			<li class="alphabet-wrap-list">A</li>
			<li class="alphabet-wrap-list">A</li>
			<li class="alphabet-wrap-list">A</li>
			<li class="alphabet-wrap-list">A</li>
			<li class="alphabet-wrap-list">A</li>
		</ul>
	</div>	
</template>

<script>
	export default {
		name : "CityAlphabet"
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
  width:.6rem
  .alphabet-wrap-list
    line-height:.4rem
    text-align:center
    color:$bgColor	
</style>