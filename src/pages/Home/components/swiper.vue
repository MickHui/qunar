<template>
	<div class="wrapper">
		<swiper :options="swiperOption" v-if="showFirst" >
			<swiper-slide  v-for="item of bannerList" :key="item.id" >
				<div>
					
				</div>
				<img class="swiper-img" :src="item.imgUrl"  />
			</swiper-slide>
			<div class="swiper-pagination"  slot="pagination"></div>
	  </swiper>
  </div>
	
</template>

<script>
	export default {
		name:'HomeSwiper',
		props:{
			bannerList:Array,
		},
		data () {
			return {
				swiperOption:{
					pagination:{
                   	 el: '.swiper-pagination'    
                   },
					loop:true,
			},
		  }
		},
		computed:{
			showFirst () {
				return this.bannerList.length
			}
		}		
	}
</script>

<style lang='stylus' scoped>
  .wrapper >>>.swiper-pagination-bullet-active
          background:#fff   
  .wrapper
    overflow:hidden
    height:0
    width:100%
    padding-bottom:32%
  .swiper-img
    width:100%
</style>