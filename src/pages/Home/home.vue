<template>
	<div>
	<home-header :city="city">
	
	</home-header>
	<home-swiper :bannerList="bannerList">
	
	</home-swiper>
	<home-icons :list="iconList">
		
	</home-icons>
	<home-recommend :recommendList="recommendList">
		
	</home-recommend>
	<home-weeked :weekendList="weekendList">
		
	</home-weeked>
	</div>
	
</template>

<script>
	import axios from 'axios'
	import HomeHeader from './components/header'
	import HomeSwiper from './components/swiper'
	import HomeIcons from './components/icons'
	import HomeRecommend from './components/recommend'
	import HomeWeeked from './components/weeked'
	export default {
		name:'Home',
		components:{
			HomeHeader,
			HomeSwiper,
			HomeIcons,
			HomeRecommend,
			HomeWeeked
		},
		data () {
			return {
				city:'',
				bannerList:[],
				iconList:[],
				recommendList : [],
				weekendList: []
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
		   	    	this.recommendList = data.recommendList 
		   	    	this.weekendList = data.weekendList
		   	    	
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