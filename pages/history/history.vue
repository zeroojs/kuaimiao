<template>
	<view class="history message-bg">
		<Navbar mode="back" title="History"></Navbar>
		<div class="history-container">
			<view class="history-group">
				<view class="history-date">April 23, 2020</view>
				<view class="history-card">
					<view class="history-card-start">
						<div class="history-card-direction">
							<view class="carcle"></view>
						</div>
						<view class="history-card-content">
							<text class="history-card-content-title">PICKUP LOCATION</text>
							<text class="history-card-content-local">Jazz Road No 23 , Malden</text>
						</view>
					</view>
					<view class="history-card-end">
						<div class="history-card-direction">
							<view class="carcle orange-carcle"></view>
						</div>
						<view class="history-card-content">
							<text class="history-card-content-title">DESTINATION LOCATION</text>
							<text class="history-card-content-local">Harvard University</text>
						</view>
					</view>
				</view>
				<view class="history-card">
					<view class="history-card-start">
						<div class="history-card-direction">
							<view class="carcle"></view>
						</div>
						<view class="history-card-content">
							<text class="history-card-content-title">PICKUP LOCATION</text>
							<text class="history-card-content-local">Jazz Road No 23 , Malden</text>
						</view>
					</view>
					<view class="history-card-end">
						<div class="history-card-direction">
							<view class="carcle orange-carcle"></view>
						</div>
						<view class="history-card-content">
							<text class="history-card-content-title">DESTINATION LOCATION</text>
							<text class="history-card-content-local">Harvard University</text>
						</view>
					</view>
				</view>
			</view>
			<view class="history-group">
			<view class="history-date">April 23, 2020</view>
			<view class="history-card">
				<view class="history-card-start">
					<div class="history-card-direction">
						<view class="carcle"></view>
					</div>
					<view class="history-card-content">
						<text class="history-card-content-title">PICKUP LOCATION</text>
						<text class="history-card-content-local">Jazz Road No 23 , Malden</text>
					</view>
				</view>
				<view class="history-card-end">
					<div class="history-card-direction">
						<view class="carcle orange-carcle"></view>
					</div>
					<view class="history-card-content">
						<text class="history-card-content-title">DESTINATION LOCATION</text>
						<text class="history-card-content-local">Harvard University</text>
					</view>
				</view>
			</view>
		</view>
		</div>
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
$text-color-dx: #8A8A8A;
$text-color-d: #B8B8B8;
.history-container {
	padding: 30rpx;
	box-sizing: border-box;
}
.message-bg {
	min-height: 100vh;
	width: 100vw;
	background-color: #F5F8FD;
}
.history-group:not(:last-child) {
	margin-bottom: 100rpx;
}
.history-date {
	color: $text-color-dx;
	font-size: 26rpx;
	margin-bottom: 30rpx;
}
.history-card {
	background-color: #fff;
	box-shadow: 0 0 50rpx rgba(0, 0, 0, 0.016);
	box-sizing: border-box;
	padding: 30rpx;
	border-radius: 8rpx;
	margin-bottom: 30rpx;
	position: relative;
	&::before {
		content: "";
		position: absolute;
		top: 62rpx;
		left: 46rpx;
		width: 0rpx;
		height: 75rpx;
		border-right: 2px dashed #CECECE;
	}
}
.history-card-direction {
	width: 100rpx;
	height: 100%;
	position: relative;
}
.carcle {
	width: 24rpx;
	height: 24rpx;
	border: 6rpx solid $uni-color-purle;
	border-radius: 50%;
	&.orange-carcle {
		border-color: orange;
		width: 20rpx;
		height: 20rpx;
		transform: translateX(2rpx);
	}
}
.history-card-content {
	display: flex;
	flex-direction: column;
	padding-top: 30rpx;
}
.history-card-content-title {
	color:$text-color-d;
	font-size: 22rpx;
}
.history-card-start,
.history-card-end {
	display: flex;
}
.history-card-start {
	padding-top: 0;
	.history-card-content {
		border-bottom: 1PX solid #FAFAFA;
		padding-top: 0;
		padding-bottom: 30rpx;
	}
}
</style>
