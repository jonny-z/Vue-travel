<template>
	<div class="header">
		<div class="header-left">
			<div class="iconfont back-icon">&#xe624;</div>
		</div>
		<div class="header-input">
			<i class="iconfont">&#xe632;</i>
			输入城市/景点/游玩
		</div>
		<router-link to='/city'>
			<div class="header-right">
				{{this.city}}
				<i class="iconfont arrow-icon">&#xe64a;</i>
			</div>
		</router-link>
	</div>
</template>

<script>
export default {
	name: 'HomeHeader',
	props: {
		city: String
	}
}
</script>

<style lang="scss" scoped>
	.header {
		display: flex;
		line-height: .86rem;
		background-color: $site-bg-color;
		color: #fff;
		.header-left {
			width: .64rem;
			float: left;
			.back-icon {
				font-size: .4rem;
				text-align: center;
			}
		}
		.header-input {
			flex: 1;
			height: .64rem;
			line-height: .64rem;
			background-color: #fff;
			border-radius: .1rem;
			margin-top: .12rem;
			margin-left: .2rem;
			padding-left: .2rem;
			color: #ccc;
		}
		.header-right {
			width: 1.24rem;
			float: right;
			text-align: center;
			color: #fff;
			.arrow-icon {
				font-size: .24rem;
				margin-left: -.04rem;
			}
		}
	}
</style>
