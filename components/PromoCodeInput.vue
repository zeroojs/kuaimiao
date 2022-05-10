<template>
	<view v-if="isUndefined(coverView)" class="promo-code-input" :class="{ disabled }">
		<cover-image class="icon icon-promo" src="../static/icon/promo.svg"></cover-image>
		<input :disabled="disabled" type="text" placeholder="INPUT PROMO CODE">
	</view>
	<cover-view v-else class="promo-code-input" :class="{ disabled }">
		<cover-image class="icon icon-promo" src="../static/icon/promo.svg"></cover-image>
		<input :disabled="disabled" type="text" placeholder="INPUT PROMO CODE">
	</cover-view>
</template>

<script>
	function isUndefined(val) {
		return val === undefined
	}
	export default {
		props: {
			coverView: String,
			disabled: Boolean
		},
		data() {
			return {
				
			};
		},
		methods: {
			isUndefined
		}
	}
</script>

<style lang="scss">
// 优惠码
.promo-code-input {
	height: 80rpx;
	display: flex;
	align-items: center;
	background-color: #F5F3F9;
	padding: 0 20rpx;
	color: $uni-color-purle;
	font-weight: 500;
	border-radius: 12rpx;
	input {
		width: calc(100% - 54rpx);
		font-size: 24rpx;
	}
	.icon-promo {
		width: 42rpx;
		margin-right: 12rpx;
	}
	&.disabled {
		background-color: #fff;
		border: 1rpx dashed #ccc;
		color: #AFAFAF;
		filter: grayscale(100%);
		opacity: .6;
		cursor: default;
	}
}
</style>
