<template>
	<view class="rate-driver cover-view-card">
		<view class="user-info">
			<image src="../../static/images/default-img.svg" class="user-avatar"></image>
			<view class="user-name">John Raymond</view>
		</view>
		<view class="rate-group">
			<view class="rate-title">
				How is your Trip ?
			</view>
			<view class="rate-summary">
				Give a rating to enhance the driver experience
			</view>
			<div class="rate-start-group">
				<image class="rate-start active" src="../../static/icon/start-active.svg" mode=""></image>
				<image class="rate-start active" src="../../static/icon/start-active.svg" mode=""></image>
				<image class="rate-start active" src="../../static/icon/start-active.svg" mode=""></image>
				<image class="rate-start active" src="../../static/icon/start-active.svg" mode=""></image>
				<image class="rate-start" src="../../static/icon/start.svg" mode=""></image>
			</div>
			<div class="rate-input-container">
				<textarea
					class="rate-input"
					placeholder="Message"
					auto-height
					cursor-spacing="30rpx"
					placeholder-style="F8F8F8"></textarea>
			</div>
			<div class="submit-rating-container">
				<button class="submit-rating-btn  btn gradient">SUBMIT RATING</button>
			</div>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			rate: {
				type: Number,
				default: 4
			}
		},
		data() {
			return {
				
			}
		}
	}
</script>

<style lang="scss">
.rate-driver {
	padding: 30rpx;
	text-align: center;
	border-radius: 32rpx;
}
.user-info {
	padding: 50rpx 0;
	border-bottom: 1rpx solid #F8F8F8;
}
.user-avatar {
	width: 120rpx;
	height: 120rpx;
	margin-bottom: 30rpx;
}
.rate-group {
	padding-top: 50rpx;
	.rate-title {
		font-size: 48rpx;
	}
}
.rate-start-group {
	padding: 50rpx 0;
	.rate-start {
		width: 68rpx;
		height: 64rpx;
	}
}
.rate-summary {
	margin-top: 30rpx;
	line-height: 48rpx;
	color: #8A8A8A;
}
.rate-input-container {
	.rate-input {
		border: 1rpx solid #F8F8F8;
		border-radius: 12rpx;
		text-align: start;
		padding: 30rpx;
		width: calc(100% - 60rpx);
		min-height: 170rpx;
	}
}
.submit-rating-container {
	padding-top: 30rpx;
	padding-bottom: 50rpx;
}
.submit-rating-btn {
	width: 100%;
}
</style>
