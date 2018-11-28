<template>
	<div class="city-list">
		<div class="city-list-item">
			<div class="city-list-title">当前城市 </div>
			 <div class="city-list-wrap">
			 	<div class="city-list-detail">
                    <button class="city-button">北京</button> 
			 	</div>
			 </div>	
			 <div class="city-list-title">热门城市 </div>
			 <div class="city-list-wrap">
			 	<div class="city-list-detail">
                    <button class="city-button">北京</button> 
			 	</div>
			 
			 </div>	
			 <div class="city-list-title">A</div>
			   <ul>
			   	  <li class="city-cityList border-bottom">阿拉善</li>
			   </ul>
		</div>
	</div>
</template>

<script>
export default {
	name:"CityList"
}
</script>

<style lang="stylus" scoped>
  .city-list
    overflow:hidden
    position:absolute
    top:1.58rem
    left:0
    right:0
    bottom:0 
	.city-list-title
	  height:.54rem
	  line-height:.54rem
	  background:#eee
	  padding-left: .2rem
	  font-size:.26rem
	  color:#666
	.city-list-wrap  
	  overflow:hidden
	  padding:.1rem .6rem .1rem .2rem
	  .city-list-detail
	    width:30%
	    float:left
	    margin:.1rem .2rem  .1rem 0
	    .city-button
	     padding:.1rem 0
	     width:100%
	     background:#fff
	     border:.02rem solid #ccc
	     border-radius:.06rem
	.city-cityList 
	  line-height:.76rem
	  padding-left:.2rem
	  font-size:.32rem
	     
  
       
        
   
</style>