<template>
	<view class="invite">
		<div class="invite-bg-top linear-bg">
			<image class="invite-img" src="../../static/images/invite-friend.svg" mode=""></image>
		</div>
		<div class="invite-bg-bottom cover-view-card">
			<div class="invite-title">Get 3 Coupons!</div>
			<div class="invite-summary">
				Just invite 3 your friend, and you will get 3 free coupons code
			</div>
			<div class="invite-input-group">
				<text class="invite-code">49V39J</text>
				<div class="invite-input-copy-btn">
					<image class="icon copy-icon" src="../../static/icon/copy.svg" mode=""></image>
				</div>
			</div>
			<div class="btn share-btn gradient">
				SHARE NOW
			</div>
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
.invite-bg-top {
	display: flex;
	justify-content: center;
	&.linear-bg {
		height: 70vh;
	}
}
.invite-img {
	width: 600rpx;
	height: 600rpx;
	padding-top: 50rpx;
}
.invite-bg-bottom {
	position: absolute;
	bottom: 100rpx;
	left: 50%;
	transform: translateX(-50%);
	padding: 50rpx 30rpx;
	border-radius: 32rpx;
}
.invite-title {
	font-size: 48rpx;
	color: $uni-color-purle;
	font-weight: 500;
	text-align: center;
}
.invite-summary {
	margin: 50rpx 0;
	text-align: center;
	color: #777777;
}
.invite-input-group {
	display: flex;
	border: 1rpx solid #F5F3F9;
	border-radius: 12rpx;
	align-items: center;
	.invite-code {
		padding: 30rpx;
		letter-spacing: 2rpx;
		font-size: 36rpx;
	}	.invite-input-copy-btn {
		width: 104rpx;
		height: 104rpx;
		background-color: #F5F3F9;
		display: flex;
		align-items: center;
		justify-content: center;
		.icon {
			width: 40rpx;
			height: 40rpx;
		}
	}
	.invite-code {
		flex: 1;
	}
}
.share-btn  {
	width: 100%;
	margin-top: 50rpx;
}
</style>
