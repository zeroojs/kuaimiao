<template>
	<view class="wlecome linear-bg">
		<swiper 
			class="wlecome-swiper"
			@change="handleChange"
			:currentIndex="currentIndex"
		>
			<swiper-item
				v-for="item in swipers"
				:key="item.title"
			>
				<view class="wlecome-swiper-item">
					<image :src="item.src" mode=""></image>
					<view class="content">
						<view class="title">{{ item.title }}</view>
						<view class="summary">
							{{ item.summary }}
						</view>
					</view>
				</view>
			</swiper-item>
		</swiper>
		<view v-if="currentIndex !== 3" class="controller">
			<view class="controller-item" :class="{ active: currentIndex === 0}"></view>
			<view class="controller-item" :class="{ active: currentIndex === 1}"></view>
			<view class="controller-item" :class="{ active: currentIndex === 2}"></view>
			<view class="controller-item" :class="{ active: currentIndex === 3}"></view>
		</view>
		<view
			v-if="currentIndex !== 3"
			class="btn"
			@click="getStart()">
			GET STARTED
		</view>
		<view v-if="currentIndex === 3" class="last-controller">
			<view @click="getStart()" class="btn local-btn">
				<view class="local-btn-content">
					<image class="icon" src="../../static/icon/local-white.svg" mode=""></image>
					Use Current Location
				</view>
			</view>
			<navigator class="more" url="../SignUp/SignUp">Select Manually</navigator>
		</view>
	</view>
	
</template>

<script>
	import KButton from '@/components/Button.vue'
	const swipers = [
		{
			src: require('../../static/images/wlecome1.svg'),
			title: 'Select Location',
			summary: 'Fusce vehicula dolor arcu, sit amet blandit dolor mollis nec. Donec viverra eleifend lacus,'
		},
		{
			src: require('../../static/images/wlecome2.svg'),
			title: 'Get a Ride',
			summary: 'Fusce vehicula dolor arcu, sit amet blandit dolor mollis nec. Donec viverra eleifend lacus,'
		},
		{
			src: require('../../static/images/wlecome3.svg'),
			title: 'Track your ride',
			summary: 'Fusce vehicula dolor arcu, sit amet blandit dolor mollis nec. Donec viverra eleifend lacus,'
		},
		{
			src: require('../../static/images/wlecome4.svg'),
			title: 'That\'s Awesome',
			summary: 'Start choose Your Location to order Taxi Car'
		}
	]
	export default {
		components: {
			KButton
		},
		data() {
			return {
				swipers,
				currentIndex: 0
			};
		},
		methods: {
			handleChange(e) {
				this.currentIndex = e.detail.current
			},
			getStart() {
				uni.navigateTo({
					url: '/pages/landing/landing'
				})
			}
		}
	}
</script>

<style scoped lang="scss">
.wlecome {
	padding-top: 200rpx;
	box-sizing: border-box;
}
.wlecome-swiper {
	height: calc(100vh - 650rpx);
}
.wlecome-swiper-item {
	height: calc(100vh - 100rpx);
	width: 100vw;
	padding-top: 100rpx;
	text-align: center
}
.title {
	text-align: center;
	color: #cecece;
	margin-bottom: 50rpx;
}
.summary {
	width: 275px;
	height: 71px;
	color: #cecece;
	font-family: "NunitoSans-Regular";
	font-size: 16px;
	font-weight: 400;
	line-height: 20px;
	letter-spacing: 0.5px;
	margin: 0 auto;
}
.content{
	margin: 50rpx auto;
}
.controller {
	margin: 100rpx auto;
	display: flex;
	align-items: center;
	justify-content: center;
	.controller-item {
		width: 20rpx;
		height: 20rpx;
		background-color: #9393F0;
		border-radius: 50%;
		margin-right: 20rpx;
		&.active {
			background-color: #fff;
		}
	}
	.controller-item:last-child {
		margin-right: 0;
	}
}
/deep/ .btn {
	margin: 25rpx auto;
}
.icon {
	width: 36rpx;
	height: 44rpx;
	margin-right: 15rpx;
}
.local-btn {
	font-size: 26rpx;
	.local-btn-content {
		display: flex;
		align-items: center;
		justify-content: center;
	}
}
.more {
	margin-top: 100rpx;
	text-decoration: underline;
	font-family: Helvetica;
	font-size: 16px;
	color: #CECECE;
	letter-spacing: 0.13px;
	text-align: center;
}
</style>
