<template>
	<div class="header">
	    <div class="header-back-button">
	    	<span class="iconfont header-back-icon ">&#xe625;</span>
	    </div>
	    <div class="header-city-serch">
	    	<i class="iconfont serch-icon">&#xe632;</i>
	           输入城市游玩主题
	    </div>
	     <router-link to="/city">
	     	<div class="header-city-button">
                           南京
	    	 <span class="iconfont header-city-icon">&#xe6bd;</span>
	        </div>
	     </router-link>
	</div>
	 
</template>

<script>
	export default {
		name:'HomeHeader',
	}
	
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl' 
  .header
    display:flex
    height:$headerHight
    background:$bgColor
    line-height:$headerHight
    color:#fff
    .header-back-button
      height:$headerHight
      width:.42rem
      padding:0 .2rem 
      text-align:center
      .header-back-icon
        font-size:.36rem
   .header-city-serch
     flex:1
     height:.64rem
     line-height:.64rem
     background:#fff
     margin:.12rem 0 0 .2rem
     border-radius:.1rem
     color:#ccc
     padding-left:.3rem
   .header-city-button 
     min-width:1.04rem 
     padding:0 .1rem
     text-align:center
     color:#fff
     .header-city-icon
       font-size:.24rem
   
     
         


</style>