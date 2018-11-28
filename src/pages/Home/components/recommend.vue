<template>
	<div class="recommend">
		<div class="recommend-title">
			热门推荐
		</div>
		<ul>
			<li class="recommend-content" v-for="item of recommendList" :key="item.id">
			    <img class="recommend-img" :src="item.imgUrl"/>
				<div class="recommend-infor">
					<h3 class="recommend-infor-title">{{item.title}}</h3>
					<p class="recommend-detail">{{item.desc}}</p>
					 <button class="recommend-btn">查看详情</button>
				</div>
			</li>
		</ul>
	</div>
	
</template>

<script>
	export default {
		name:'HomeRecommend',
		props:{
			recommendList:Array
		}
	}
</script>

<style lang="stylus" scoped>
  @import '~styles/ellipsis.styl'     
	  .recommend-title
	    line-height:.8rem
	    background:#eee
	    margin-top:.2rem
	    padding-left:.2rem
	    font-size:.36rem
	  .recommend-content
	    display:flex 
	    overflow:hidden
	    height:1.9rem
	    .recommend-img
	      height:1.7rem
	      width:1.7rem
	      padding:.1rem
	  .recommend-infor
	    flex:1
	    padding:.1rem
	    min-width:0
	    .recommend-infor-title	     
	      line-height:.56rem
	      font-size:.32rem
	      ellipsis()
	    .recommend-detail 
	      line-height:.44rem
	      color:#ccc
	      ellipsis()
	    .recommend-btn
	      background:orange
	      padding: 0 .2rem
	      margin-top:.2rem
	      border-radius:.06rem 
	      color:#fff 
     

</style>