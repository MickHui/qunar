<template>
	<div >
		<div class="city-search">
		   <input v-model="keyword" class="city-search-input" type="text" placeholder="输入城市名或拼音" />
		</div>
		<div class="search-content" v-show="keyword">
			<ul>
				<li class="search-list border-bottom"
					v-for="item of list"
					:key="item.id"
					@click='changeCity(item.name)'
				>
				   {{item.name}}
				</li>
				<li class="search-list border-bottom"  v-if="hasNokeyword">
					没有您要找的内容
				</li>
			</ul>
		</div>
	</div>	
</template>

<script>
import Bscroll from 'better-scroll'
export default {
	name : "CitySearch",
	props:{
		cities : Object
	},
	data () {
		return {
			keyword :'',
			list:[],
			timer:null
		}
	},
	computed:{
		hasNokeyword () {
			return !this.list.length	
		}
	},
	watch:{
		keyword () {
		  if(this.timer){
		  	clearTimeout(this.timer)
		  }
		  if(!this.keyword){
		  	this.list = []
		  }
		  this.timer = setTimeout(()=>{
		  	const result = []
		  	for (let i in this.cities){
		  		this.cities[i].forEach((value)=>{
		  			if(value.spell.indexOf(this.keyword) > -1 || value.name.indexOf(this.keyword)>-1){
		  				result.push(value)
		  			}
		  		})
		  	}
		  	 this.list = result
		  },100)
			
		}
	},
	methods:{
		 changeCity (city) {
			this.$store.dispatch('changeCity',city)
			this.$router.push('/')
		},
	},
	mounted () {
		this.scroll = new Bscroll('.search-content')
	}
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
.city-search
  height:.72rem
  padding:0 .1rem
  background:$bgColor
  display:flex
  .city-search-input
    flex:1
    height:.6rem
    margin-top:.06rem
    border-radius:.06rem
    text-align:center
    color:#666
    padding:0 .2rem
.search-content
  z-index:9
  overflow:hidden
  position:absolute
  top:1.58rem
  right:0
  left:0
  bottom:0
  background:#eee
  .search-list
    line-height:.62rem
    padding-left:.2rem
    background:#fff
    color:#666
    
</style>