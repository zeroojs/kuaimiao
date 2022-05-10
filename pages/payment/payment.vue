<template>
	<view class="payment message-bg">
		<Navbar mode="back" title="Payment"></Navbar>
		<div class="payment-banner">
			<PayCard class="payment-banner-item" type="purle"/>
			<PayCard class="payment-banner-item" type="primary"/>
			<PayCard class="payment-banner-item" type="origin"/>
		</div>
		<view class="list payment-list">
			<view class="list-title">
				Recent Activities
			</view>
			<RecentActivitieCard
				v-for="item in recentActivities"
				:key="item.id"
				:name="item.name"
				:leave="item.leave"
				:price="item.price"
				:begin="item.begin"
				:target="item.target"
			/>
		</view>
	</view>
</template>

<script>
	import PayCard from '../../components/PayCard.vue'
	import RecentActivitieCard from '../../components/RecentActivitieCard.vue'
	const recentActivities = [
		{
			id: 'r-1',
			name: 'Alexander William',
			leave: 4,
			price: 20,
			begin: 'Jazz Road No 23, Malden',
			target: 'Harvard University'
		},
		{
			id: 'r-2',
			name: 'James Rogue',
			leave: 5,
			price: 16,
			begin: 'Harvard University',
			target: 'Kenangan Coffee, California'
		},
		{
			id: 'r-3',
			name: 'Alex Mansion',
			leave: 5,
			price: 9,
			begin: 'Kenangan Coffee, California',
			target: 'Jazz Road No 23, Malden'
		}
	]
	export default {
		components: {
			PayCard,
			RecentActivitieCard
		},
		data() {
			return {
				recentActivities
			};
		}
	}
</script>

<style lang="scss">
.payment-list {
	padding: 30rpx;
}
.payment-banner {
	margin-bottom: 30rpx;
	margin-top: 60rpx;
	position: relative;
	height: 340rpx;
	.payment-banner-item {
		position: absolute;
		width: 600rpx;
		height: 340rpx;
		&:nth-child(1) {
			left: -540rpx;
		}
		&:nth-child(2) {
			left: 50%;
			transform: translateX(-50%);
		}
		&:nth-child(3) {
			left: auto;
			right: -540rpx;
		}
	}
}
.message-bg {
	min-height: 100vh;
	width: 100vw;
	background-color: #F5F8FD;
}
.list-title {
	font-size: 24rpx;
	color: #8A8A8A;
	margin-bottom: 30rpx;
}
</style>
