<template>
    <div>
			 <router-link 
				 tag="div" 
				 to="/"
				 class="header-abs"
				 v-show="showHide"
			 >
				<span class="iconfont header-back-icon ">&#xe625;</span> 
			 </router-link>
			 <div class="header-fixed" 
			      v-show="!showHide"
						:style= "opacityStyle" 
			>
				<router-link to="/">
				<div class="iconfont header-icon ">&#xe625;</div> 				 
				</router-link>
				景点详情
			 </div>
		</div>
</template>
<script>
	export default {
		name:'DetailHeader',
		data () {
			return {
				showHide:true,
				opacityStyle:{
					opacity:0
				}
			}
		},
		methods:{
		    handleScroll () {
					const top = document.documentElement.scrollTop
					 if( top > 60 ){
						 let opacity = top / 140
						 opacity = opacity > 1 ? 1 : opacity
							this.opacityStyle  = { opacity }
							this.showHide = false
					 }else {
						   this.showHide = true
					 }
				}
		},
		activated () {
			window.addEventListener('scroll',this.handleScroll)
		},
		deactivated () {
			window.removeEventListener('scroll',this.handleScroll)
		},
		

	}
</script>
<style lang="stylus" scoped>
   @import '~styles/varibles.styl'
  .header-abs
		 position:absolute
		 top:.2rem
		 left:.2rem
		 height:.8rem
		 width:.8rem
		 border-radius:.4rem
		 line-height:.8rem
		 text-align:center
		 background:rgba(0,0,0,.8)
		 .header-back-icon
				color:#fff
				font-size:.36rem
	.header-fixed
		 position:fixed 
		 z-index:2 
		 top:0
		 left:0
		 right:0
		 height:$headerHight
		 background:$bgColor
		 line-height:$headerHight
		 color:#fff
		 text-align:center
		 font-size:.32rem
		 .header-icon
				position:absolute
				top:0
				left:0
				color:#fff
				width:.8rem
				height:.8rem
				font-size:.36rem
		
</style>