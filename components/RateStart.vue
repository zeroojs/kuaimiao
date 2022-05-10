<template>
	<view>
		<view class="rate-start-group">
			<image
				v-for="(item, index) in [1, 2, 3, 4, 5]"
				:key="`rate-start-${index}`"
				:style="startStyle"
				:class="['rate-start', index < leave ? 'active' : '']"
				:src="index < leave ? '../static/icon/start-active.svg' : '../static/icon/start.svg'"
				mode=""></image>
		</view>
	</view>
</template>

<script>
	export default {
		props: {
			size: {
				type: String,
				default: '68rpx'
			},
			leave: {
				type: Number,
				default: 3
			}
		},
		data() {
			return {
				
			};
		},
		computed: {
			startStyle() {
				return `width: ${this.size};height: ${this.size};`
			}
		}
	}
</script>

<style lang="scss">
.rate-start-group {
	.rate-start {
		width: 68rpx;
		height: 64rpx;
	}
}
</style>
