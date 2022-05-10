<template>
	<view class="fixed-card">
		<slot></slot>
	</view>
</template>
 
<script>
	export default {
		data() {
			return {
				
			};
		}
	}
</script>

<style lang="scss">
.fixed-card {
	width: 680rpx;
	height: 112rpx;
	border-radius: 6rpx;
	background-color: #FFF;
	// box-shadow: 0 0 40rpx #858488;
	margin: 0 auto;
}
</style>
