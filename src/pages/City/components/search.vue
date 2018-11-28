<template>
	<div >
		<div class="city-search">
		   <input class="city-search-input" type="text" placeholder="输入城市名或拼音" />
		</div>
	</div>
	
</template>

<script>
	export default {
		name : "CitySearch"
	}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.city-search
  height:.72rem
  padding:0 .1rem
  background:$bgColor
  display:flex
  .city-search-input
    flex:1
    height:.6rem
    margin-top:.06rem
    border-radius:.06rem
    text-align:center
    color:#666
    padding:0 .2rem

</style>