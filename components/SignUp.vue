<template>
	<view class="sign-in">
		<view @click="$emit('showController', 'overview')" class="back-btn">
			<image class="icon arrow-left" src="../static/icon/arrow-left.svg" mode=""></image>
		</view>
		<view class="card">
			<text class="title">Sign Up</text>
			<view class="summary">Fusce vehicula dolor arcu, sit amet blandit dolor mollis</view>
			<view class="form">
				<view class="form-item">
					<text class="form-label">EMAIL</text>
					<input v-model="email" type="text" value="" />
					<image class="icon icon-opps" src="../static/icon/opps.svg" mode=""></image>
				</view>
				<view class="form-item">
					<text class="form-label">PASSWORD</text>
					<input placeholder="enter password" type="text" value="" />
				</view>
				<view class="form-item">
					<text class="form-label">CONFIRM PASSWORD</text>
					<input placeholder="retype password" type="text" value="" />
				</view>
			</view>
			<view @click="signUp" class="sign-in-btn btn gradient">SIGN UP</view>
		</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				email: 'customemail.com',
				password: ''
			};
		},
		methods: {
			back() {
				uni.navigateBack({
					delta: 1,
					animationType: 'fade-out'
				})
			},
			signUp() { // 注册
				this.$emit('showController', 'verifyStep')
			}
		}
	}
</script>

<style lang="scss" scoped>
.sign-in {
	padding-top: 80rpx;
	box-sizing: border-box;
}
.card {
	width: calc(100% - 72rpx);
	height: 570rpx * 2;
	min-height: 400rpx;
	box-shadow: 0 0 45rpx rgba(133, 132, 136, .15);
	border-radius: 17rpx;
	background-color: #fff;
	padding: 80rpx 60rpx;
	box-sizing: border-box;
	margin: 0 auto;
	position: relative;
}
.title {
	color: #6732CB;
	font-size: 64rpx;
}
.summary {
	margin: 30rpx 0 130rpx 0;
	color: #777777;
	font-size: $uni-font-size-lg;
}
.icon {
	position: absolute;
	width: 44rpx;
	height: 44rpx;
}
.form-item {
	margin-bottom: 30rpx;
	position: relative;
	.form-label {
		color: $uni-color-purle;
		font-weight: 400;
		letter-spacing: .1em;
		margin-bottom: 30rpx;
		font-size: 26rpx;
	}
	.icon-opps {
		right: 0;
		bottom: 30rpx;
	}
	.forgot-password {
		text-align: right;
		color: $uni-color-purle;
		display: block;
		font-size: 26rpx;
	}
}
input {
	border-bottom: 1PX solid #E9E9E9;
	line-height: 48rpx * 2;
	height: 48rpx * 2;
}
input:-moz-placeholder,
input:-ms-input-placeholder {
	color: #E9E9E9;
}
// 按钮 #3C7CD2 - #6732CB
.sign-in-btn {
	position: absolute;
	bottom: 80rpx;
}
.back-btn {
	padding-bottom: 40rpx;
	.icon {
		position: unset;
		margin-left: 36rpx;
	}
}
</style>
