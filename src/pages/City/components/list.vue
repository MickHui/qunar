<template>
	<div class="wrapper">
		<div class="content">
		  <div class="item">
		  	 <div class="item-title border-bottom">当前位置</div>
		  	  <div class="item-list">
		  	  	 <div class="item-list-wrapper" >
		  	  	 	<div class="item-city">北京</div>
		  	  	 </div>  	
		  	  </div>
		  </div>
		  <div class="item">
		  	 <div class="item-title">热门城市</div>
		  	   <div class="item-list">
		  	  	 <div class="item-list-wrapper" v-for="item of hotCities" :key="item.id">
		  	  	 	<div class="item-city">{{item.name}}</div>
		  	  	 </div>
		  	  </div>
		  </div>
		  <div class="item" v-for="(item,key) in cities" :key="key">
		  	 <div class="item-title">{{key}}</div>
		  	  <ul class="border-bottom" v-for="innerItem of item ">
		  	  	<li class="item-detail">{{innerItem.name}}</li>
		  	  </ul>
		  </div>
		
		   
		  
		
		
		
		
		
		</div>	
	</div>
</template>

<script>
import Bscroll from 'better-scroll'	
export default {
	name:"CityList",
	props:{
		hotCities:Array,
		cities:{
			type:Object
		}
	},
	mounted () {
		this.scroll = new Bscroll('.wrapper')
	}
} 
</script>

<style lang="stylus" scoped>
.wrapper
   overflow:hidden
   position:absolute
   top:1.58rem
   right:0
   left:0
   bottom:0 
   .item-title
     line-height:.54rem
     background:#eee
     padding-left:.2rem
   .item-list
     overflow:hidden
     padding:.1rem .6rem .1rem .2rem
     .item-list-wrapper
       width:33.33%
       float:left 
       .item-city
         padding:.1rem 0
         border:.02rem solid #ccc
         border-radius:.1rem
         text-align:center
         margin:.1rem
	.item-detail
	   line-height:.72rem
	   padding-left:.2rem     

	
		     
	  
       
     
   
</style>