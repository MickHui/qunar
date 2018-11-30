<template>
	<div>
		<detail-banner
			:sightName = "sightName"
			:bannerImg = "bannerImg"
			:gallaryImgs = 'gallaryImgs'	
		>
		</detail-banner>
	</div>
</template>

<script>
import axios from 'axios'	
import DetailBanner from './components/banner'

export default{
	name:'Detail',
	components:{
		DetailBanner,	
	},
	data () {
		return {
			sightName:'',
			bannerImg:'',
			gallaryImgs:[]
			
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
			 }
		}
	},
	mounted () {
		this.getDetailInfor()
	}
}
</script>

<style>
	
	
	
</style>