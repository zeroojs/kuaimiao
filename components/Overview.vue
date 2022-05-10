<template>
	<view class="overview">
		<view class="landing-avatar">
			<Avatar/>
		</view>
		<view class="card landing-card">
			<text class="title">Get Started</text>
			<view class="summary">Fusce vehicula dolor arcu, sit amet blandit dolor mollis</view>
			<view class="btn landing-btn landing-btn--purle">
				Continue With Email
			</view>
			<view class="btn landing-btn landing-btn--blue">Continue With Facebook</view>
			<view class="btn landing-btn landing-btn--red">Continue With Google</view>
		</view>
	</view>
</template>

<script>
	import KButton from './Button.vue'
	import Avatar from './Avatar.vue'
	export default {
		components: {
			Avatar,
			KButton
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.overview {
	height: 100vh;
	width: 100vw;
	position: relative;
	padding-top: 200rpx;
	box-sizing: border-box;
}
.landing-avatar {
	display: flex;
	justify-content: center;
	box-sizing: content-box;
	padding: 90rpx 0;
}
.title {
	color: #6732CB;
	font-size: 64rpx;
}
.summary {
	margin: 30rpx 0 130rpx 0;
	color: #777777;
	font-size: $uni-font-size-lg;
}
.landing-card {
	padding: 60rpx;
	box-sizing: border-box;
	margin: 0 auto;
	/deep/ .btn {
		box-shadow: none;
		letter-spacing: unset;
	}
}
.card {
	width: calc(100% - 72rpx);
	min-height: 400rpx;
	box-shadow: 0 0 45rpx rgba(133, 132, 136, .15);
	border-radius: 17rpx;
	background-color: #fff;
}
.landing-btn {
	width: 100%;
	display: block;
	padding: 0;
	margin-bottom: 40rpx;
}
.landing-btn--purle.btn {
	background: $uni-color-purle;
}
.landing-btn--blue.btn {
	background: #325BCB
}
.landing-btn--red.btn {
	background: #CB3232;
}
</style>
