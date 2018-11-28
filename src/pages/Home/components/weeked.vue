<template>
	<div class="weeked">
       <h3 class="weeked-title" >周末去哪</h3>
		<ul>
			<li class="weeked-item" v-for="item of weekendList" :key="item.id">
				<div class="weeked-img-wrapper">
					<img class="weeked-img" :src="item.imgUrl" :alt="item.title" />
				</div>
				<div class="weeked-infor">
				 	 <h3 class="weeked-infor-title">{{item.title}}</h3>
				 	 <p class="weeked-infor-detail">{{item.desc}}</p>
			    </div>
			</li>
		</ul> 
	</div>	
</template>

<script>
	export default {
		name:'HomeWeeked',
		props:{
			weekendList : Array
		}
	}
</script>

<style lang='stylus' scoped>
@import '~styles/ellipsis.styl'
.weeked-title
  line-height:.8rem
  padding-left:.2rem
  background:#eee
  font-size:.32rem 
.weeked-img-wrapper
  overflow:hidden
  height:0
  padding-bottom:37.09%	
  .weeked-img
    width:100% 
.weeked-infor
  padding:.1rem
  min-width:0
  .weeked-infor-title
    line-height:.52rem
    font-size:.32rem
  .weeked-infor-detail
    line-height:.4rem
    font-size:.24rem
    color:#999 
    ellipsis() 
</style>
	
			