<template>
	   <div>
	   	  <div class="item" v-for="(item,index) of list" :key="index">
				   <div class="item-title border-bottom" >
						 <span class="item-icon"></span>
						   {{item.title}}
					 </div>
					 <div class="item-chi" v-if="item.children">
						<detail-list :list="item.children ">
						 </detail-list> 
					 </div>
				
				</div>
	   </div>
</template>
m-chi
<script>
	export default {
		name:"DetailList",
		props:{
			list:Array
		}
	}
</script>

<style lang="stylus" scoped>
  .item
    padding-left:.2rem
		.item-title
			height:.8rem
			line-height:.8rem
			font-size:.32rem
			.item-icon
				display:inline-block
				height:.36rem
				width:.36rem
				background:url(http://s.qunarzz.com/piao/image/touch/sight/detail.png) 0 -.40rem  no-repeat
				background-size: .4rem 3rem
				margin-right: .05rem
		.item-chi
		  font-size:.32rem
		
		
	
	
			
	  
	
	
</style>