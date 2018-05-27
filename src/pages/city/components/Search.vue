<template>
	<div class="search">
		<input class="search-input" type="text" placeholder="输入城市名或拼音">
	</div>
</template>

<script>
export default {
	name: 'CitySearch'
}
</script>

<style lang="scss" scoped>
	.search {
		height: .72rem;
		background-color: $site-bg-color;
		padding: 0 .1rem;
		.search-input {
			width: 100%;
			height: .62rem;
			line-height: .62rem;
			border-radius: .06rem;
			text-align: center;
			padding: 0 .1rem;
			color: #666;
			box-sizing: border-box;
		}
	}
</style>
