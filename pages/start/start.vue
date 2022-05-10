<template>
	<view class="start linear-bg" @click="aotuInWelcomePage()">
		<image class="logo app-logo" src="../../static/images/logo.svg" mode=""></image>
		<view class="app-name">Kuai Mao</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		mounted() {
			aotuInWelcomePage()
		},
		methods: {
			aotuInWelcomePage
		}
	}
	// 自动进入欢迎页面
	function aotuInWelcomePage() {
		const timer = setTimeout(() => {
			uni.navigateTo({
				url: '/pages/wlecome/wlecome',
				animationType: 'pop-in',
				animationDuration: 200
			})
			clearTimeout(timer)
		}, 1500)
	}
</script>

<style lang="scss">
.start {
	width: 100vw;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	font-size: 48rpx;
	color: #fff;
}
.logo {
	width: 228rpx;
	height: 242rpx;
	margin-bottom: 60rpx;
}
</style>
