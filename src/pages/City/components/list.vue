<template>
	<div class="wrapper">
		<div class="content">
		  <div class="item">
		  	 <div class="item-title border-bottom">当前位置</div>
		  	  <div class="item-list">
		  	  	 <div class="item-list-wrapper" >
		  	  	 	<div class="item-city">{{this.currentCity}}</div>
		  	  	 </div>  	
		  	  </div>
		  </div>
		  <div class="item">
		  	 <div class="item-title">热门城市</div>
		  	   <div class="item-list">
		  	  	 <div class="item-list-wrapper" 
		  	  	 	  v-for="item of hotCities" 
		  	  	 	  :key="item.id"
		  	  	 	  @click="changeCity(item.name)"
		  	  	 	  
		  	  	 >
		  	  	 	<div class="item-city">{{item.name}}</div>
		  	  	 </div>
		  	  </div>
		  </div>
		  <div class="item" 
		  	v-for="(item,key) in cities" 
		  	:key="key"
		  	:ref="key"
		  >
		  	 <div class="item-title">{{key}}</div>
		  	  <ul class="border-bottom" 
		  	  	  v-for="innerItem of item "
		  	  	  @click="changeCity(innerItem.name)"
		  	  >
		  	  	<li class="item-detail">{{innerItem.name}}</li>
		  	  </ul>
		  </div>	
		</div>	
	</div>
</template>

<script>
import Bscroll from 'better-scroll'	
import { mapState,mapMutations } from 'vuex'
export default {
	name:"CityList",
	props:{
		hotCities:Array,
		cities:Object,
		letter:String
	},
	computed : {
		...mapState({
			currentCity:"city"
		})
	},
	methods : {
		changeCity (city) {
			this.$store.dispatch('changeCity',city)
			this.$router.push('/')
           
		},
	},
	mounted () {
		this.scroll = new Bscroll('.wrapper')
	},
	watch:{
		letter () {
			if(this.letter){
				const element = this.$refs[this.letter][0];
				this.scroll.scrollToElement(element)	
			}
		}
	},
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