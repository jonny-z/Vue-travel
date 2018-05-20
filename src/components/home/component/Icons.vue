<template>
	<div class="icons">
		<swiper>
			<swiper-slide v-for="(paging,index) of pages" :key="index">
				<div class="icon" v-for="item of paging" :key="item.id">
					<div class="icon-img">
						<img :src="item.imgUrl">
					</div>
					<p class="icon-desc">{{item.desc}}</p>
				</div>
			</swiper-slide>
		</swiper>
	</div>
</template>

<script>
export default {
	name: 'HomeIcons',
	data () {
		return {
			iconList: [{
				id: '0001',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
				desc: '景点门票'
			}, {
				id: '0002',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
				desc: '滑雪季节'
			}, {
				id: '0003',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
				desc: '泡温泉'
			}, {
				id: '0004',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
				desc: '动植园'
			}, {
				id: '0005',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
				desc: '一日游'
			}, {
				id: '0006',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
				desc: '景门票'
			}, {
				id: '0007',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
				desc: '点门票'
			}, {
				id: '0008',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
				desc: '景点票'
			}, {
				id: '0009',
				imgUrl: 'http://img1.qunarzz.com/piao/fusion/1803/95/f3dd6c383aeb3b02.png',
				desc: '景点门'
			}]
		}
	},
	computed: {
		pages () {
			const pages = []
			this.iconList.forEach((item, index) => {
				const page = Math.floor(index / 8)
				if (!pages[page]) {
					pages[page] = []
				}
				pages[page].push(item)
			})
			return pages
		}
	}
}
</script>

<style lang="scss" scoped>
	.icons {
		height: 0;
		padding-bottom: 50%;
		overflow: hidden;
		.icon {
			overflow: hidden;
			width: 25%;
			height: 0;
			padding-bottom: 25%;
			float: left;
			position: relative;
			.icon-img {
				box-sizing: border-box;
				padding: .1rem;
				position: absolute;
				left: 0;
				right: 0;
				top: 0;
				bottom: .44rem;
				> img {
					display: block;
					margin: 0 auto;
					height: 100%;
				}
			}
			.icon-desc {
				position: absolute;
				left: 0;
				right: 0;
				bottom: 0;
				height: .44rem;
				line-height: .44rem;
				text-align: center;
				color: $site-color;
				@include ellipsis;
			}
		}
	}
</style>
