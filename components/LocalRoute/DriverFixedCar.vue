<template>
	<cover-view class="driver-fixed-car cover-view-card">
		<cover-view class="media">
			<cover-view class="media-avatar">
				<cover-image src="../../static/images/avatar.svg"></cover-image>
			</cover-view>
			<div class="media-body">
				<cover-view class="media-name">Alexander William</cover-view>
				<cover-view class="media-start">
					<cover-image class="icon icon-start" src="../../static/icon/start-active.svg"></cover-image>
					<cover-image class="icon icon-start" src="../../static/icon/start-active.svg"></cover-image>
					<cover-image class="icon icon-start" src="../../static/icon/start-active.svg"></cover-image>
					<cover-image class="icon icon-start" src="../../static/icon/start-active.svg"></cover-image>
					<cover-image class="icon icon-start" src="../../static/icon/start.svg"></cover-image>
				</cover-view>
			</div>
		</cover-view>
		<cover-view class="car-number">
			Toyota Avanza B 3323 SS
		</cover-view>
		<cover-view class="car-summary">
			<cover-view class="car-summary-item">
				<cover-view class="car-summary-title">
					DISTANCE
				</cover-view>
				<cover-view class="car-summary-content">
					0.5km
				</cover-view>
			</cover-view>
			<cover-view class="car-summary-item">
				<cover-view class="car-summary-title">
					TIME
				</cover-view>
				<cover-view class="car-summary-content">
					30 mins
				</cover-view>
			</cover-view>
			<cover-view class="car-summary-item">
				<cover-view class="car-summary-title">
					PRICE
				</cover-view>
				<cover-view class="car-summary-content">
					$20.00
				</cover-view>
			</cover-view>
		</cover-view>
		<cover-view 
			v-show="!contact" 
			class="btn gradient continue-btn"
			@click="booking()">CONTINUE</cover-view>
		<cover-view v-show="contact" class="conatct-btn-group">
			<cover-view class="btn success-btn">
				<cover-image class="icon icon-call" src="../../static/icon/call.svg"></cover-image>
				CALL
			</cover-view>
			<cover-view @click="chat()" class="btn gradient">
				<cover-image class="icon icon-chat" src="../../static/icon/chat.svg"></cover-image>
				CHAT
			</cover-view>
		</cover-view>
	</cover-view>
</template>

<script>
	export default {
		props: {
			contact: {
				type: Boolean,
				default: true
			}
		},
		data() {
			return {
				booking() {
					this.$emit('booking')
				}
			};
		},
		methods: {
			chat() {
				uni.navigateTo({
					url: '/pages/message/message'
				})
			}
		}
	}
</script>

<style lang="scss">
$border: 1rpx solid #FAFAFA;
.driver-fixed-car {
	position: fixed;
	bottom: 68rpx;
}
.icon {
	width: 32rpx;
	height: 34rpx;
}
.media-start {
	display: flex;
	align-items: center;
	margin-top: 12rpx;
}
.media {
	display: flex;
	align-items: center;
	padding: 30rpx 0 40rpx;
	border-bottom: $border;
}
.media-avatar {
	width: 120rpx;
	height: 120rpx;
	margin-right: 30rpx;
}
.car-number {
	height: 80rpx;
	line-height: 80rpx;
	border-bottom: $border;
	font-size: 24rpx;
	text-align: center;
	letter-spacing: 2rpx;
}
.car-summary {
	display: flex;
	align-items: center;
	justify-content: space-between;
	text-align: center;
	font-size: 24rpx;
	padding: 40rpx 0;
	letter-spacing: 2rpx;
	.car-summary-title {
		color: #B8B8B8;
		margin-bottom: 12rpx;
	}
}
.continue-btn {
	box-shadow: none;
	margin: 10rpx auto 20rpx;
	width: 100%;
}
.conatct-btn-group {
	display: flex;
	.btn {
		box-shadow: none;
		margin-bottom: 20rpx;
		display: flex;
		align-items: center;
		justify-content: center;
		&:first-child {
			margin-right: 20rpx;
		}
		&:last-child {
			margin-left: 20rpx;
		}
		&.success-btn {
			background: #3FC05E;
		}
		.icon {
			margin-right: 20rpx;
		}
	}
}
</style>
