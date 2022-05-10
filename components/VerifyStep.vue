<template>
	<view class="verify-step">
		<view class="card">
			<text class="card-title">Complete Step</text>
			<view class="card-summary">Fusce vehicula dolor arcu, sit amet blandit dolor mollis</view>
			<view class="media-input">
				<view class="media-input-head">
					<image class="icon icon-us" src="../static/icon/us.svg" mode=""></image>
					<text>+1</text>
				</view>
				<input v-model="tel" type="text" value="" />
			</view>
			<view @click="getCode" class="sign-in-btn btn gradient">GET VERIFY CODE</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				tel: ''
			};
		},
		methods: {
			getCode() {
				this.$emit('showController', 'enterCode')
			}
		}
	}
</script>

<style lang="scss">
.card {
	width: calc(100% - 72rpx);
	height: 412rpx * 2;
	min-height: 400rpx;
	box-shadow: 0 0 45rpx rgba(133, 132, 136, .15);
	border-radius: 17rpx;
	background-color: #fff;
	padding: 80rpx 60rpx;
	box-sizing: border-box;
	margin: 0 auto;
	position: relative;
	.card-title {
		color: #6732CB;
		font-size: 64rpx;
	}
	.card-summary {
		margin: 30rpx 0 130rpx 0;
		color: #777777;
		font-size: $uni-font-size-lg;
	}
}

.icon {
	width: 86rpx;
	height: 48rpx;
}
input {
	border-bottom: 1PX solid #E9E9E9;
	line-height: 48rpx * 2;
	height: 48rpx * 2;
}
.media-input {
	position: relative;
	.media-input-head {
		position: absolute;
		display: flex;
		align-items: flex-end;
		bottom: 30rpx;
		.icon-us {
			margin-right: 30rpx;
		}
	}
	input {
		padding-left: 162rpx;
	}
}
.sign-in-btn {
	position: absolute;
	bottom: 80rpx;
}
</style>
