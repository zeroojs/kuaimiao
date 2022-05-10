<template>
	<view class="recent-activitle-card media-card">
		<view class="media-card-top driver-info">
			<view class="media-card-top-left">
				<image class="driver-avatar" src="../static/images/default-img.svg" mode=""></image>
			</view>
			<view class="media-card-top-enter">
				<view class="driver-info-title">{{ name }}</view>
				<view class="starts-group">
					<RateStart size="26rpx" :leave="leave"/>
				</view>
			</view>
			<view class="media-card-top-right">
				<view class="price-tag">${{ Number(price).toFixed(2) }}</view>
			</view>
		</view>
		<view class="media-card-bottom">
			<view class="media-card-bottom-left">{{ begin }}</view>
			<view class="media-card-bottom-center">
				<image class="icon arrow-left-purle-icon" src="../static/icon/arrow-right-purle.svg" mode=""></image>
			</view>
			<view class="media-card-bottom-right">{{ target }}</view>
		</view>
	</view>
</template>

<script>
	import RateStart from './RateStart.vue'
	export default {
		components: {
			RateStart
		},
		props: {
			name: String,
			begin: String,
			target: String,
			price: Number,
			leave: Number
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.recent-activitle-card {
	color: #565656;
}
.media-card {
	background-color: #fff;
	box-shadow: 0 0 50rpx rgba(0, 0, 0, 0.016);
	box-sizing: border-box;
	padding: 30rpx;
	border-radius: 8rpx;
	margin-bottom: 30rpx;
	// width: calc(100% - 60rpx);
}
.media-card-top {
	width: 100%;
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding-bottom: 15rpx;
	border-bottom: 1rpx solid #FAFAFA;
	.media-card-top-enter {
		flex: 1;
		margin: 0 30rpx;
	}
}
.driver-avatar {
	width: 80rpx;
	height: 80rpx;
}
.price-tag {
	color: $uni-color-purle;
	background-color: #F3F3FF;
	padding: 12rpx 20rpx;
	border-radius: 50rpx;
	font-size: 24rpx;
}
// 底部
.media-card-bottom {
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding-top: 20rpx;
}
.media-card-botto-center {
	width: 40rpx;
	margin: 0 30rpx;
}
.media-card-bottom-left,
.media-card-bottom-right {
	width: calc((100% - 120rpx) / 2);
	font-size: 24rpx;
}
.arrow-left-purle-icon {
	width: 30rpx;
	height: 30rpx;
}
// 评分
.rate-start-group {
	/deep/ .rate-start {
		width: 26rpx;
		height: 26rpx;
	}
}
</style>
