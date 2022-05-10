<template>
	<view class="book-success cover-view-card">
		<view class="book-success-title">Booking Successfully</view>
		<image class="icon icon-gradent-check" src="../../static/icon/gradent-check.svg" mode=""></image>
		<view class="book-success-summary">
			Your booking has been confirmation, driver will be come in 3 minutes
		</view>
		<view @click="$emit('done')" class="btn gradient done-btn">DONE</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.icon.icon-gradent-check {
	width: 250rpx;
	height: 250rpx;
	transform: translateY(24rpx);
}
.book-success {
	text-align: center;
	border-radius: 32rpx;
	padding: 60rpx;
}
.book-success-summary {
	margin: 0 0 40rpx;
	font-size: 28rpx;
}
.done-btn {
	width: 100%;
}
</style>
