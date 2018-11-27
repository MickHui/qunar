<template>
	<div>
	<home-header :city="city">
	
	</home-header>
	<home-swiper :bannerList="bannerList">
	
	</home-swiper>
	</div>
	
</template>

<script>
	import axios from 'axios'
	import HomeHeader from './components/header'
	import HomeSwiper from './components/swiper'
	export default {
		name:'Home',
		components:{
			HomeHeader,
			HomeSwiper
		},
		data () {
			return {
				city:'',
				bannerList:[]	
			}
		},
		methods:{
			getHomeInfor () {
			  axios.get('api/index.json').then(
			     this.getHomeInforSucc
			 )
		   },
		   getHomeInforSucc (res) {
		   	    res = res.data 
		   	    if(res.ret && res.data){
		   	    	const data =res.data
		   	    	this.city = data.city
		   	    	this.bannerList = data.swiperList
		   	    }
		   }
		},
		mounted () {
			this.getHomeInfor ()
		}
	}
	
</script>

<style>
</style>