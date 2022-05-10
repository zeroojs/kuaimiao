<template>
	<view class="notifications message-bg">
		<view
			v-for="item in notifications"
			:key="item.id"
			class="media-card"
			@click="selected(item)">
			<view class="media-card-left">
				<div class="media-icon-container" :class="item.type">
					<image class="media-icon" :src="item.icon" mode=""></image>
				</div>
			</view>
			<view class="media-card-right">
				<view class="media-card-title">{{ item.title }}</view>
				<view class="media-card-content">{{ item.content }}</view>
			</view>
		</view>
	</view>
</template>

<script>
	const notifications = [
		{
			id: 'notify-item1',
			type: 'coupons',
			icon: '../../static/icon/coupons.svg',
			title: 'Get 3 Free Coupons Now!',
			path: '/pages/invite/invite',
			content: 'Just invite 3 your friend, and you will get 3 free coupons code'
		},
		{
			id: 'notify-item2',
			type: 'success',
			icon: '../../static/icon/book-success.svg',
			title: 'Booking Successfully!',
			content: 'Your booking has been confirmation, driver will be come in 3 minutes'
		},
		{
			id: 'notify-item3',
			type: 'coupons',
			icon: '../../static/icon/coupons.svg',
			title: 'Only today!',
			content: 'Get discount 20% for all destination, use 20PERCENT coupon code'
		},
		{
			id: 'notify-item4',
			type: 'transaction',
			icon: '../../static/icon/translation.svg',
			title: 'Transaction complete',
			content: 'Thank you for trip with ovlet, come back again John'
		}
	]
	export default {
		data() {
			return {
				notifications
			};
		},
		methods: {
			selected(item) {
				uni.navigateTo({
					url: item.path
				})
			}
		}
	}
</script>

<style lang="scss">
.notifications {
	padding: 30rpx;
}
.media-card {
	background-color: #fff;
	box-shadow: 0 0 50rpx rgba(0, 0, 0, 0.016);
	box-sizing: border-box;
	padding: 50rpx;
	border-radius: 8rpx;
	margin-bottom: 30rpx;
	display: flex;
	align-items: flex-start;
	width: calc(100% - 60rpx);
}
.media-icon-container {
	width: 80rpx;
	height: 80rpx;
	background-color: #EDE3FF;
	border-radius: 50%;
	display: flex;
	align-items: center;
	justify-content: center;
	margin-right: 30rpx;
	&.success {
		background-color: #E1FFE8;
	}
	&.transaction {
		background-color: #FFEDE3;
	}
}
.media-icon {
	width: 42rpx * 1.5;
	height: 32rpx * 1.5;
}
.media-icon-container.success .media-icon {
	width: 42rpx;
	height: 32rpx;
}
.media-card-title {
	color: #3D3D3D;
}
.media-card-content {
	color: #B8B8B8;
	font-size: 24rpx;
}
</style>
