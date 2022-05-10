<template>
	<view class="enter-code">
		<view class="card">
			<text class="card-title">Enter Code</text>
			<view class="card-summary">Enter the four digit code we sent to +123 456 789</view>
			<view class="code-input-group">
				<input type="text" value="2" :maxlength="1"/>
				<input type="text" value="5" :maxlength="1"/>
				<input type="text" value="" :maxlength="1"/>
				<input type="text" value="" :maxlength="1"/>
			</view>
			<view @click="verifyCode" class="sign-in-btn btn gradient">CONTINUE</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		},
		methods: {
			verifyCode() {
				uni.navigateTo({
					url: '/pages/map/map'
				})
			}
		}
	}
</script>

<style lang="scss">
.enter-code {
	padding-top: 200rpx;
	box-sizing: border-box;
}
.card {
	width: calc(100% - 72rpx);
	height: 412rpx * 2;
	min-height: 400rpx;
	box-shadow: 0 0 45rpx rgba(133, 132, 136, .15);
	border-radius: 17rpx;
	background-color: #fff;
	padding: 80rpx 60rpx;
	box-sizing: border-box;
	margin: 0 auto;
	position: relative;
	.card-title {
		color: #6732CB;
		font-size: 64rpx;
	}
	.card-summary {
		margin: 30rpx 0 60rpx 0;
		color: #777777;
		font-size: $uni-font-size-lg;
	}
}
.code-input-group {
	display: flex;
	align-items: center;
	justify-content: center;
	margin-bottom: 60rpx;
	input {
		display: block;
		width: 110rpx;
		height: 178rpx;
		background-color: #F5F3F9;
		margin: 20rpx;
		text-align: center;
		border-radius: 6rpx;
		font-size: 48rpx;
		font-weight: 500;
		color: #9C90B4;
	}
}
</style>
