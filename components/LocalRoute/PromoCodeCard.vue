<template>
	<cover-view class="promo-code-card cover-view-card">
		<cover-view class="close-container">
			<cover-image class="icon icon-close" src="../../static/icon/close.svg"></cover-image>
		</cover-view>
		<cover-view class="promo-code-title">
			INPUT PROMO CODE
		</cover-view>
		<PromoCodeInput disabled/>
		<cover-view @click="applyCar()" class="btn apply-btn gradient">APPLY</cover-view>
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
				
			};
		},
		methods: {
			applyCar() {
				this.$emit('showController', 'localInput,driver')
			}
		}
	}
</script>

<style lang="scss">
.icon {
	width: 30rpx;
	height: 30rpx;
	&.icon-close {
		cursor: pointer;
	}
}
.promo-code-card {
	position: fixed;
	bottom: 68rpx;
	// padding: 40rpx 30rpx;
}
.promo-code-title {
	margin-bottom: 20rpx;
}
.apply-btn {
	width: 100%;
	margin-top: 40rpx;
	box-shadow: unset;
}
.close-container {
	display: flex;
	justify-content: flex-end;
}
</style>
