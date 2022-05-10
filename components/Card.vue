<template>
	<view class="card">
		<slot>123</slot>
	</view>
</template>

<style lang="scss">
.card {
	width: calc(100% - 36rpx);
	min-height: 400rpx;
	box-shadow: 0 5rpx 30rpx rgba(133, 132, 136, .1);
	border-radius: 17rpx;
}
</style>
