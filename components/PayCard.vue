<template>
	<view :class="['pay-card', `pay-card--${type}`]">
		<view class="pay-card-head">
			<div class="pay-card-chip"></div>
			<div class="pay-card-logo">
				<image class="icon visa-icon" src="../static/icon/visa.svg" mode=""></image>
			</div>
		</view>
		<view class="pay-card-body">1499 3948 0093 2000</view>
		<view class="pay-card-footer">
			<view>
				JOHN RAYMEND
			</view>
			<view class="pay-card-footer-right">
				05/25
			</view>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			type: String
		},
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.icon {
	width: 120rpx;
	height: 38rpx;
}
.pay-card {
	width: 600rpx;
	height: 340rpx;
	background: linear-gradient(45deg, #299CEE, #3272CB);
	border-radius: 12rpx;
	padding: 60rpx;
	box-sizing: border-box;
	color: #fff;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	&.pay-card--purle {
		background: linear-gradient(45deg, #E229EE, #A632CB);
	}
	&.pay-card--origin {
		background: linear-gradient(45deg, #EE6E29, #CB9032);
	}
}
.pay-card-head,
.pay-card-footer {
	display: flex;
	align-items: center;
	justify-content: space-between;
}
.pay-card-body {
	margin-bottom: 30rpx;
}
.pay-card-chip {
	width: 80rpx;
	height: 66rpx;
	background-color: #E3B229;
	border-radius: 12rpx;
}
</style>
