<template>
	<div class="wrapper">
		<swiper :options="swiperOption">
			<swiper-slide v-for="item of swiperList" :key="item.id">
				<img class="swiper-img"  :src="item.imgUrl" />
			</swiper-slide>
			<div class="swiper-pagination"  slot="pagination"></div>
		</swiper>
	</div>
</template>

<script>
export default {
	name: 'HomeSwiper',
	data () {
		return {
			swiperOption: {
				pagination: {
					el: '.swiper-pagination'
				},
				loop: true
			},
			swiperList: [
				{
					id: 1,
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1805/e5/59fad13a64807d02.jpg_750x200_713ae984.jpg'
				},
				{
					id: 2,
					imgUrl: 'http://img1.qunarzz.com/piao/fusion/1710/14/ef15a6b3739e4b02.jpg_750x200_e55ba592.jpg'
				}
			]
		}
	}
}
</script>

<style lang="scss" scoped>
.wrapper /deep/ .swiper-pagination-bullet-active {
	background: #fff;
}
.wrapper {
	overflow: hidden;
	width: 100%;
	height: 0;
	padding-bottom: 26.666667%;
	background: #eee;
	.swiper-img {
		width: 100%
	}
}
</style>
