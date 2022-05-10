<template>
	<view class="setting message-bg">
		<view class="setting-media-card media-card">
			<div class="media-card-left">
				<image class="user-avatar" src="../../static/images/default-img.svg" mode=""></image>
			</div>
			<div class="media-card-center">
				<div class="media-card-title">
					John Raymend
				</div>
				<div class="media-content user-email">
					john raymend@gmail.com
				</div>
			</div>
			<div class="media-card-right">
				<image class="icon arrow-left-icon" src="../../static/icon/arrow-right.svg" mode=""></image>
			</div>
		</view>
		<view
			v-for="item in menu"
			:key="item.path"
			class="media-card">
			<view class="media-card-left">
				<image class="icon notify-icon" :src="item.icon" mode=""></image>
			</view>
			<view class="media-card-center">{{ item.name }}</view>
			<div class="media-card-right">
				<image class="icon arrow-left-icon" src="../../static/icon/arrow-right.svg" mode=""></image>
			</div>
		</view>
	</view>
</template>

<script>
	const menu = [
		{
			path: '/notifications',
			name: 'Notifications',
			icon: '../../static/icon/notify.svg'
		},
		{
			path: '/security',
			name: 'Security',
			icon: '../../static/icon/security.svg'
		},
		{
			path: '/language',
			name: 'Language',
			icon: '../../static/icon/global.svg'
		},
		{
			path: '/privacy',
			name: 'Privacy & Policy',
			icon: '../../static/icon/privacy.svg'
		},
		{
			path: '/terms',
			name: 'Terms & Conditions',
			icon: '../../static/icon/terms.svg'
		},
		{
			path: '/contact-us',
			name: 'Contact Us',
			icon: '../../static/icon/email-purle.svg'
		},
	]
	export default {
		data() {
			return {
				menu
			};
		}
	}
</script>

<style lang="scss">
.setting {
	padding: 30rpx;
	color: #3D3D3D;
}
.media-card {
	background-color: #fff;
	box-shadow: 0 0 50rpx rgba(0, 0, 0, 0.016);
	box-sizing: border-box;
	padding: 30rpx;
	border-radius: 8rpx;
	margin-bottom: 30rpx;
	display: flex;
	align-items: center;
	justify-content: space-between;
	width: calc(100% - 60rpx);
}
.media-card-center {
	flex: 1;
	margin: 0 30rpx;
}
.media-card-title {
	margin-bottom: 6rpx;
}
.user-email {
	color: #B8B8B8;
	font-size: 24rpx;
}
.icon {
	width: 36rpx;
	height: 32rpx;
	&.arrow-left-icon {
		width: 12rpx;
		height: 24rpx;
	}
}
.user-avatar {
	width: 96rpx;
	height: 96rpx;
}
</style>
