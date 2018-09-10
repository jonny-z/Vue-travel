<template>
	<div>
		<home-header :city="city"></home-header>
		<home-swiper :list="swiperList"></home-swiper>
		<home-icons :list="iconList"></home-icons>
		<home-recomment :list="recommendList"></home-recomment>
		<home-weekend :list="weekendList"></home-weekend>
	</div>
</template>

<script>
import HomeHeader from './component/Header'
import HomeSwiper from './component/Swiper'
import HomeIcons from './component/Icons'
import HomeRecomment from './component/Recomment'
import HomeWeekend from './component/Weekend'
import axios from 'axios'

export default {
	name: 'Home',
	data () {
		return {
			city: '',
			swiperList: [],
			iconList: [],
			recommendList: [],
			weekendList: []
		}
	},
	components: {
		HomeHeader,
		HomeSwiper,
		HomeIcons,
		HomeRecomment,
		HomeWeekend
	},
	methods: {
		getHomeInfo () {
			axios.get('/api/index.json').then(this.getHomeInfoSucc)
		},
		getHomeInfoSucc (res) {
			res = res.data
			if (res.ret && res.data) {
				const data = res.data
				this.city = data.city
				this.swiperList = data.swiperList
				this.iconList = data.iconList
				this.recommendList = data.recommendList
				this.weekendList = data.weekendList
			}
		}
	},
	mounted () {
		this.getHomeInfo()
	}
}
</script>

<style lang="scss">

</style>
