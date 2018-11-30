<template>
	<div class="wrapper">
	    <div class="banner" @click="handleShowBanner">
	         <img class="banner-img" :src="bannerImg"  />
	         <div class="banner-infor">
	         	<div class="banner-num"><i class="iconfont banner-icon">&#xe631;</i>{{this.gallaryImgs.length}}</div>
	         	<p class="banner-title">{{this.sightName}}</p>
	         </div>
	    </div>
	      <fade-animation>
	      	<gallary
	       	v-show="showSwiper"
	       	@close = 'handleCloseBanner'
	       	:gallaryImgs="gallaryImgs"
	       >
	       </gallary>
       </fade-animation>
	</div>
</template>

<script>
import Gallary from 'common/Gallary/gallary'
import FadeAnimation from 'common/Fade/fadeAnimation'
export default {
  name:"DetailBanner",
  props:{
  	sightName:String,
  	bannerImg:String,
  	gallaryImgs:Array
  },
  components:{
  	Gallary,
  	FadeAnimation
  },
  data () {
  	return {
  		showSwiper : false
  	}
  },
  methods : {
  	handleShowBanner () {
  		this.showSwiper =true
  	},
  	handleCloseBanner () {
  		this.showSwiper =false
  	},
  }
}
</script>

<style lang="stylus" scoped>
   .banner
     position:relative
     overflow:hidden
     height:0
     padding-bottom:55%
     .banner-img
       width:100%
     .banner-infor
       position:absolute
       right:0
       left:0
       bottom:0
       background-image:linear-gradient(top,rgba(0,0,0,0), rgba(0,0,0,.8))
	   .banner-num
	     line-height:.4rem
	     color:#fff
	     background:rgba(0,0,0,.8)
	     width:.6rem
	     padding:0 .2rem
	     border-radius:.6rem
	     font-size:.24rem
	     text-align:center
	     margin-left:.2rem
	     .banner-icon
	       font-size:.24rem
	    .banner-title
	      line-height:.56rem
	      color:#fff
	      padding-left:.2rem
	      font-size:.32rem
</style>