<template>
	<div class="header">
	    <div class="header-back-button">
	    	<span class="iconfont header-back-icon ">&#xe625;</span>
	    </div>
	    <div class="header-city-serch">
	    	<i class="iconfont serch-icon">&#xe632;</i>
	          <input class="header-city-input" type="text" placeholder=" 输入城市游玩主题" />
	    </div>
	     <router-link to="/city">
	     	<div class="header-city-button">
                   {{this.city}} 
	    	 <span class="iconfont header-city-icon">&#xe6bd;</span>
	        </div>
	     </router-link>
	</div>
	 
</template>

<script>
	export default {
		name:'HomeHeader',
		props:{
			city:String
		}
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
      padding:0 .2rem 
      text-align:center
      .header-back-icon
        font-size:.36rem
   .header-city-serch
     flex:1
     display:flex
     height:.64rem
     line-height:.64rem
     background:#fff
     margin:.12rem 0 0 0
     border-radius:.1rem
     color:#ccc
     .serch-icon
       display:block
       height:.64rem
       width:.64rem
       text-align:center
       float:left
     .header-city-input
       flex:1
       height:.64rem
       line-height:.64rem
       border-radius:.1rem
       border:0
       margin-bottom:.07rem
       padding:0 .2rem 0 0   
   .header-city-button 
     min-width:1.04rem 
     padding:0 .1rem
     text-align:center
     color:#fff
     .header-city-icon
       font-size:.24rem
   
     
         


</style>