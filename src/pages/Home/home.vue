<template>
	<div>
	<home-header :city="city">
	
	</home-header>
	<home-swiper :bannerList="bannerList">
	
	</home-swiper>
	<home-icons :list="iconList"></home-icons>
	</div>
	
</template>

<script>
	import axios from 'axios'
	import HomeHeader from './components/header'
	import HomeSwiper from './components/swiper'
	import HomeIcons from './components/icons'
	export default {
		name:'Home',
		components:{
			HomeHeader,
			HomeSwiper,
			HomeIcons
		},
		data () {
			return {
				city:'',
				bannerList:[],
				iconList:[]
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
		   	    	this.iconList = data.iconList
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