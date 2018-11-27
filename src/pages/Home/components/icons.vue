<template>
	<div class="wrapper">
		<swiper :options="swiperOption" v-if="showFirst">
		    <swiper-slide v-for="(page,index) of pages" :key="index">
		    	<div class="icon-list-infor" v-for="item of page" :key="item.id" >
		    		<div class="icon-list-img"  >
		    			<img class="img-style" :src="item.imgUrl"/>
		    		</div>
		    		<div class="icon-list-title">
		    		{{item.desc}}
		    		</div>
		    	</div>
		    </swiper-slide>
		    <div class="swiper-pagination"  slot="pagination"></div>  
	  </swiper> 
	</div>
	
</template>

<script>
	export default {
		name : 'HomeIcons',
		props : {
			list : Array
		},
		data ( ) {
			return {
				swiperOption : {
                   pagination:{
                   	 el: '.swiper-pagination'    
                   },
                   loop:true
				}
			}
		},
		computed : {
			pages () {
				const pages = []
			    this.list.forEach((item,index) =>{
					const page = Math.floor(index/8)
					if(!pages[page]){
						pages[page] = []
					}
					pages[page].push(item)
			 })
			  return pages
			},
			showFirst () {
				return this.list.length
			}
		}
	}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
   .wrapper
     overflow:hidden
     height:0
     padding-bottom:50%
     .icon-list-infor
       position:relative 
       float:left
       width:25%
       height:0
       padding-bottom:25%
       .icon-list-img
         position:absolute
         left:0
         right:0        
         bottom:.6rem
         text-align:center
         box-sizing:border-box
         padding-top:.1rem
         .img-style
           width:65%
       .icon-list-title
         position:absolute
         bottom:0
         height:.6rem 
         width:100%
         line-height:.6rem
         text-align:center
         color:$TxtColor    
</style>