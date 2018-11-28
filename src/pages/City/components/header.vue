<template>
	<div class="city-header">
	    <div class="header-back-button" @click="handleBack">
	    	<span class="iconfont header-back-icon ">&#xe625;</span>
	    </div>
	    <div class="city-header-title ">
	       <span>城市选择</span>
	    </div>
	</div>
	
	
</template>

<script>
	export default {
		name:'CityHeader',
		methods : {
			handleBack () {
				this.$router.push('/')
			}
	  }
	}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.city-header
  display:flex
  height:$headerHight
  line-height:$headerHight
  background:$bgColor
  .header-back-button
    line-height:$headerHight
    padding:0 .2rem 
    text-align:center
    color:#fff
    .header-back-icon
      font-size:.36rem
      font-weight:bolder
  .city-header-title 
    flex:1
    padding-left:2.4rem
    font-size:.36rem 
    color:#fff
     
</style>