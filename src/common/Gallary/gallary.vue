<template>
	<div class="container"  @click="handleCloseBanner">
	   <div class="wrapper" >
	      <swiper :options="swiperOptions" >
		    <swiper-slide >
		    	<img class="swiperImg" src=" http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg"/>
		    </swiper-slide>
   
	          <swiper-slide >
		    	<img class="swiperImg" src=" http://img1.qunarzz.com/sight/p0/201404/23/04b92c99462687fa1ba45c1b5ba4ad77.jpg_600x330_bf9c4904.jpg"/>
		    </swiper-slide>
		    <div class="swiper-pagination"  slot="pagination"></div>	 
	      </swiper>
	   </div>	
	</div>

</template>

<script>
	export default {
		name:'gallary',
		data () {
			return {
				swiperOptions : {
					pagination : '.swiper-pagination',
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