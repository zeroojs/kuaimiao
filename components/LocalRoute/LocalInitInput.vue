<template>
	<cover-view @click="inputPath()" class="local-init-input cover-view-card">
		<cover-view  class="card-left">
			<cover-image class="icon icon-car" src="../../static/icon/car.svg" mode=""></cover-image>
			<cover-view>Where are you going ?</cover-view>
		</cover-view >
		<cover-view  class="card-right">
			<cover-image class="icon icon-local" src="../../static/icon/local.svg" mode=""></cover-image>
		</cover-view >
	</cover-view>
</template>

<script>
	export default {
		data() {
			return {}
		},
		methods: {
			inputPath() {
				this.$emit('showController', 'localInput')
			}
		}
	}
</script>

<style lang="scss" scoped>
.local-init-input {
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding: 20rpx 30rpx;
	.icon {
		width: 48rpx;
		height: 36rpx;
	}
}
.card-left,
.card-right {
	height: 112rpx - 40rpx;
	display: flex;
	align-items: center;
}
.card-left {
	.icon-car {
		margin-right: 40rpx;
	}
}
.card-right {
	border-left: 1rpx solid #E9E9E9;
	padding-left: 20rpx;
}
</style>
