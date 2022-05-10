<template>
	<cover-view class="lcoal-input cover-view-card">
		<cover-view class="lcoal-input-item lcoal-input-top">
			<cover-view class="icon icon-circle"></cover-view>
			<cover-view>Jazz Road No 23 , Malden</cover-view>
		</cover-view>
		<cover-view class="lcoal-input-item lcoal-input-bottom">
			<cover-view class="icon icon-circle"></cover-view>
			<input
				v-model="target"
				type="text"
				placeholder="Enter your Destination" />
		</cover-view>
	</cover-view>
</template>

<script>
	export default {
		// model: {
		// 	prop: 'value',
		// 	event: 'change'
		// },
		props: {
			value: String
		},
		data() {
			return {
				target: ''
			};
		},
		watch: {
			target: function(val) {
				this.$emit('handleChangeTarget', val)
			},
			value: function(val) {
				this.target = val
			}
		}
	}
</script>

<style lang="scss">
.cover-view-card {
	box-shadow: 0 0 20rpx rgba($color: #858488, $alpha: 0.1);
	width: 680rpx;
	height: 261rpx;
	border-radius: 6rpx;
	background-color: #FFF;
	margin: 0 auto;
	box-sizing: border-box;
	line-height: 112rpx - 30rpx;
	font-weight: 300;
	display: flex;
	flex-direction: column;
	justify-content: flex-start;
	align-items: flex-start;
	position: relative;
	&::before {
		content: " ";
		position: absolute;
		left: 55rpx;
		top: 80rpx;
		height: 261rpx - 60rpx - 115rpx;
		width: 3rpx;
		box-sizing: border-box;
		border-right: 3rpx dashed $uni-color-purle;
	}
	.lcoal-input-item {
		height: 80rpx;
		display: flex;
		align-items: center;
		width: 100%;
		line-height: unset;
		.icon-circle {
			display: block;
			width: 30rpx;
			height: 30rpx;
			border-radius: 50%;
			box-sizing: border-box;
			margin-right: 30rpx;
		}
	}
	.lcoal-input-top {
		height: auto;
		color: $uni-color-purle;
		font-weight: 500;
		margin-top: 30rpx;
		margin-bottom: 45rpx;
		.icon-circle {
			background-color: $uni-color-purle;
		}
	}
	.lcoal-input-bottom {
		input {
			display: block;
			width: calc(100% - 60rpx);
			height: 80rpx;
			padding: 0 24rpx;
			background-color: #F5F3F9;
		}
		.icon-circle {
			border: 6rpx solid #FF6833;
		}
	}
}
</style>
