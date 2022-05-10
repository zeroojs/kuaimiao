<template>
	<view class="message message-bg">
		<Navbar>
			<div class="message-navbar flex">
				<text @click="back()" class="back-btn">返回</text>
				<text class="phone-btn">
					<!-- 电话 -->
				</text>
				<view class="message-contact flex">
					<image class="default-img" src="../../static/images/default-img.svg" mode=""></image>
					<div class="user-name">Alexander William</div>
				</view>
			</div>
		</Navbar>
		<div class="message-chat-container">
			<div class="message-chat-timestamp">Today, 12:10 AM</div>
			<div class="message-chat-horiztion target">
				<div class="message-chat message-chat-purple">
					Where are your positions?
				</div>
			</div>
			<div class="message-chat-horiztion self">
				<div class="message-chat message-chat-white">
					I am in lobby
				</div>
			</div>
			<div class="message-chat-horiztion self">
				<div class="message-chat message-chat-white">
					I wear yellow jackets
				</div>
			</div>
			<div class="message-chat-horiztion target">
				<div class="message-chat message-chat-purple">
					Okay, please wait. I will arrive in 2 minutes
				</div>
			</div>
			<div class="message-chat-horiztion self">
				<div class="message-chat message-chat-white">
					Ok
				</div>
			</div>
		</div>
		<div class="message-input">
			<input placeholder="Type Messages…" type="text" value="" />
			<div class="send-message-btn">
				<image class="icon icon-send-message" src="../../static/icon/send-message-btn.svg" mode=""></image>
			</div>
		</div>
	</view>
</template>

<script>
	export default {
		components: {
		},
		data() {
			return {
				
			};
		},
		methods: {
			back() {
				uni.navigateBack()
			}
		}
	}
</script>

<style lang="scss">
.flex {
	display: flex;
	align-items: center;
}
// 导航栏
.default-img,
.phone-btn {
	width: 64rpx;
	height: 64rpx;
}
.default-img {
	margin-right: 24rpx;
}
.message-chat-timestamp {
	text-align: center;
	color: #8A8A8A;
	font-size: 24rpx;
	margin-bottom: 60rpx;
}
.message-chat-container {
	padding: 36rpx;
	// height: calc(100vh - 260rpx);
	height: calc(100vh - 420rpx);
}
.message-chat-horiztion {
	margin-bottom: 40rpx;
	text-align: right;
	&.target {
		text-align: left;
	}
}
.message-chat-horiztion.target + .message-chat-horiztion.target {
	margin-top: 0;
}
.message-chat-horiztion.target + .message-chat-horiztion.self {
	margin-top: 60rpx;
}
.message-chat-horiztion.self + .message-chat-horiztion.self {
	margin-top: 0;
}
.message-chat-horiztion.self + .message-chat-horiztion.target {
	margin-top: 60rpx;
}
.message-chat {
	max-width: 60%;
	box-shadow: 0 10rpx 30rpx rgba(133, 132, 136, .1);
	padding: 15rpx 30rpx;
	display: inline-block;
	position: relative;
	z-index: 3;
	background-color: $uni-color-purle;
	color: #fff;
	border-radius: 0 12rpx 12rpx;
	transform: translateX(15rpx);
	line-height: 50rpx;
	&::before {
		content: " ";
		z-index: 2;
		position: absolute;
		width: 30rpx;
		height: 30rpx;
		border: 30rpx solid $uni-color-purle;
		border-right-color: transparent;
		border-left-color: transparent;
		border-bottom-color: transparent;
		box-sizing: border-box;
		border-radius: 12rpx;
		top: 0;
		left: -25rpx;
	}
}
.message-chat-white {
	background-color: #fff;
	color: #8A8A8A;
	transform: translateX(-15rpx);
	&::before {
		border-top-color: #fff;
		left: auto;
		right: -25rpx;
	}
}
// 发送信息输入框
.message-input {
	height: 100rpx;
	width: calc(100% - 72rpx);
	margin: 0 auto;
	box-shadow: 0 0 30rpx rgba(133, 132, 136, .2);
	display: flex;
	align-items: center;
	padding: 0 30rpx;
	box-sizing: border-box;
	border-radius: 12rpx;
	input {
		height: 100rpx;
		padding: 0 30rpx;
		flex: 1;
		font-size: 24rpx;
	}
	.send-message-btn {
		width: 60rpx;
		height: 60rpx;
		background-color: $uni-color-purle;
		border-radius: 50%;
		display: flex;
		align-items: center;
		justify-content: center;
		.icon-send-message {
			width: 30rpx;
			height: 30rpx;
		}
	}
}
</style>
