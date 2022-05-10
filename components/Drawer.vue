<template>
	<view class="drawer drawer-menu linear-bg ">
		<view class="user-info">
			<image src="../static/images/default-img.svg" class="user-avatar"></image>
			<view class="user-name">John Raymond</view>
		</view>
		<view class="drawer-menu-group">
			<view 
				v-for="item in menus" 
				:key="item.name" 
				class="drawer-menu-item"
				@click="selectedMenu(item)">
				<image class="drawer-menu-icon" src="../static/icon/home.svg" mode=""></image>
				<text>{{ item.name  }}</text>
			</view>
		</view>
	</view>
</template>

<script>
	const menus = [
		{
			name: 'Home',
			path: '/',
			icon: ''
		},
		{
			name: 'Payment',
			path: '/pages/payment/payment',
			icon: ''
		},
		{
			name: 'History',
			path: '/pages/history/history',
			icon: ''
		},
		{
			name: 'Notifications',
			path: '/pages/notifications/notifications',
			icon: ''
		},
		{
			name: 'Invite Friend',
			path: '/',
			icon: ''
		},
		{
			name: 'Setting',
			path: '/pages/setting/setting',
			icon: ''
		},
		{
			name: 'Logout',
			path: '/',
			icon: ''
		}
	]
	let timer = null
	export default {
		props: {
			show: Boolean
		},
		data() {
			return {
				hide: true,
				menus
			};
		},
		watch: {
			show: function(val) {
				timer = setTimeout(() => {
					this.hide = !val
					clearTimeout(timer)
				}, 300)
			}
		},
		onUnload() {
			timer && clearTimeout(timer)
		},
		methods: {
			selectedMenu(item) {
				console.log(item)
				uni.navigateTo({
					url: item.path
				})
				this.$emit('close')
			}
		}
	}
</script>

<style lang="scss">
.drawer {
	width: 80vw;
	height: 100vh;
	position: fixed;
	top: 0;
	left: 0;
	z-index: 9999;
	color: #fff;
	box-shadow: 0 15rpx 100rpx #333;
}
.user-info {
	text-align: center;
	padding: 100rpx 0;
}
.user-avatar {
	width: 120rpx;
	height: 120rpx;
	margin-bottom: 30rpx;
}
.drawer-menu-group {
	padding: 0 100rpx;
}
.drawer-menu-item {
	display: flex;
	margin-bottom: 50rpx;
	&:last-child {
		margin-bottom: 0;
	}
}
.drawer-menu-icon {
	width: 36rpx;
	height: 40rpx;
	margin-right: 30rpx;
}
</style>
