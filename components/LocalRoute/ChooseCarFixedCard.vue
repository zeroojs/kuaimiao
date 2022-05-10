<template>
	<cover-view class="choose-car cover-view-card">
		<cover-view class="choose-car-title">
			CHOOSE CAR
		</cover-view>
		<cover-view class="car-radio-group">
			<cover-view class="car-radio active">
				<cover-image class="icon icon-sedan-car" src="../../static/icon/sedan-car.svg"></cover-image>
				<cover-view class="car-name">SEDAN</cover-view>
				<cover-view class="people-num">
					<cover-image class="icon icon-people" src="../../static/icon/people.svg"></cover-image>
					<cover-view class="people-num-value">1 - 2</cover-view>
				</cover-view>
			</cover-view>
			<cover-view class="car-radio">
				<cover-image class="icon icon-sedan-car" src="../../static/icon/suv-car.svg"></cover-image>
				<cover-view class="car-name">SUV</cover-view>
				<cover-view class="people-num">
					<cover-image class="icon icon-people" src="../../static/icon/people.svg"></cover-image>
					<cover-view class="people-num-value">1 - 2</cover-view>
				</cover-view>
			</cover-view>
			<cover-view class="car-radio">
				<cover-image class="icon icon-sedan-car" src="../../static/icon/van-car.svg"></cover-image>
				<cover-view class="car-name">VAN</cover-view>
				<cover-view class="people-num">
					<cover-image class="icon icon-people" src="../../static/icon/people.svg"></cover-image>
					<cover-view class="people-num-value">1 - 2</cover-view>
				</cover-view>
			</cover-view>
		</cover-view>
		<cover-view class="choose-car-title-bar">
			<cover-view class="choose-car-title">
				TRIP FEE
			</cover-view>
			<cover-view class="choose-car-price">
				$20.00
			</cover-view>
		</cover-view>
		<PromoCodeInput :disabled="disabled"/>
		<cover-view @click="request()" class="btn request-btn gradient">
			REQUEST
		</cover-view>
	</cover-view>
</template>

<script>
	import PromoCodeInput from '../PromoCodeInput.vue'
	export default {
		components: {
			PromoCodeInput
		},
		data() {
			return {
				disabled: false
			};
		},
		methods: {
			request() {
				this.$emit('showApply')
			}
		}
	}
</script>

<style lang="scss">
$border: 1rpx solid #FAFAFA;
.choose-car {
	position: fixed;
	bottom: 68rpx;
}
.icon {
	width: 108rpx;
	height: 38rpx;
	&.icon-people {
		width: 25rpx;
		margin-right: 12rpx;
	}
}
.choose-car-title {
	margin-bottom: 20rpx;
	font-size: 28rpx;
}
.car-radio-group {
	display: flex;
	padding-bottom: 20rpx;
	margin-bottom: 20rpx;
	border-bottom: $border;
	.car-radio:nth-child(2) {
		margin: 0 20rpx;
	}
}
.car-radio {
	width: 198rpx;
	height: 150rpx;
	background-color: #F9F9F9;
	border-radius: 12rpx;
	overflow: hidden;
	display: flex;
	flex-direction: column;
	align-items: center;
	justify-content: center;
	padding: 12rpx 12rpx 0;
	&.active {
		color: $uni-color-purle;
		background-color: #F5F3F9;
	}
}
.car-name {
	font-size: 26rpx;
	margin-top: 20rpx;
}
.people-num {
	display: flex;
	align-items: center;
}
.people-num-value {
	font-size: 22rpx;
}
.choose-car-title-bar {
	display: flex;
	justify-content: space-between;
	.choose-car-price {
		color: #FF8834;
		font-size: 28rpx;
	}
}
.request-btn {
	margin: 20rpx auto 0;
	width: 100%;
	box-shadow: unset;
}
</style>
