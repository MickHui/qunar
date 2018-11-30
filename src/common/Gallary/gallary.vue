<template>
	<div class="container"  @click="handleCloseBanner">
	   <div class="wrapper" >
	      <swiper :options="swiperOptions" >
		    <swiper-slide v-for="(item,index) of gallaryImgs" :key="index">
		    	<img class="swiperImg" :src="item"/>
		    </swiper-slide>
		    <div class="swiper-pagination"  slot="pagination"></div>	 
	      </swiper>
	   </div>	
	</div>

</template>

<script>
	export default {
		name:'gallary',
		props:{
			gallaryImgs:Array
		},
		data () {
			return {
				swiperOptions : {
					pagination : {
						el:'.swiper-pagination'
					},
					paginationType:'fraction',
					observeParents:true,
					observer:true,
					loop:true
				}
			}
		},
		methods:{
			handleCloseBanner ( ) {
				this.$emit("close")
			}
		}
	}
</script>

<style lang="stylus" scoped>
 .container >>> .swiper-container
   overflow: inherit
 .container
   z-index:99
   display:flex
   flex-direction:column
   justify-content:center
   position:fixed
   top:0
   right:0
   left:0
   bottom:0
   background:#000
	 .wrapper
	   height:0
	   width:100%
	   padding-bottom:100%
	   .swiperImg
	     width:100%
	   .swiper-pagination
	      color:#fff
	      bottom:-1rem


</style>