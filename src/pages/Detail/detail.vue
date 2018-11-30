<template>
	<div>
		<detail-banner
			:sightName = "sightName"
			:bannerImg = "bannerImg"
			:gallaryImgs = 'gallaryImgs'	
		>
		</detail-banner>
	
	   <detail-header></detail-header>
			 <div class="content">
				 <detail-list :list="list"></detail-list>
			 </div>
		 
	</div>
</template>

<script>
import axios from 'axios'	
import DetailBanner from './components/banner'
import DetailList from './components/list'
import DetailHeader from './components/header'

export default{
	name:'Detail',
	components:{
		DetailBanner,
		DetailList,
		DetailHeader
	},
	data () {
		return {
			sightName:'',
			bannerImg:'',
			gallaryImgs:[],
			list:[]
			
		}
	},
	methods:{
		getDetailInfor () {
			axios.get("/api/detail.json").then(this.getDetailSucc)
		},
		getDetailSucc (res) {
			 res = res.data
			 if(res.ret && res.data ){
			 	 const data = res.data
			 	   this.sightName = data.sightName
			 	   this.bannerImg = data.bannerImg
			 	   this.gallaryImgs = data.gallaryImgs
			 	   this.list = data.categoryList
			 }
		}
	},
	mounted () {
		this.getDetailInfor()
	}
}
</script>

<style lang="stylus" scoped>
	.content
	  height:20rem
	
	
</style>