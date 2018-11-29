<template>
	<div>
      <city-header >
      </city-header>
      <city-search :cities = 'cities'></city-search>
      <city-list 
      	:hotCities="hotCities"
      	:cities = 'cities'
      	:letter = "letter"
      	
      ></city-list>
      <city-alphabet 
      	:cities = 'cities'
      	@change = "hangleLettersClick"
      >
      </city-alphabet>
	</div>
</template>

<script>
import CityHeader from './components/header'
import CitySearch from './components/search'
import CityList from './components/list'
import CityAlphabet from './components/alphabet'
import axios from 'axios'

export default {
	name:'City',
	components : {
		CityHeader,
		CitySearch,
		CityList,
		CityAlphabet
	},
	data ( ) {
		return {
		hotCities:[],
		cities:{},
		letter:''
		}
	},
	methods:{
		getCityInfor () {
			axios.get ('api/city.json').then(this.getCityInforSucc)
		},
		getCityInforSucc (res) {
			res = res.data
			if(res.ret && res.data){
				const data = res.data
				this.hotCities = data.hotCities
			    this.cities = data.cities
			}
		},
		hangleLettersClick (letter) {
			this.letter = letter
		}
	},
	
	mounted () {
		this.getCityInfor()
	}
}
</script>

<style lang="stylus" scoped>

 

</style>