<template>
	<view class="navbar":style="{ height: customBar + 'px' }">
		<div class="status-bar" :style="{ height: statusBar+ 'px' }">
			
		</div>
		<div class="custom-bar" :style="{ height: (customBar - statusBar) + 'px' }">
			<slot>
				<div v-if="mode === 'menu'" class="custom-bar-left" @click="openDrawer()">
					菜单
				</div>
				<div v-else class="custom-bar-left" @click="back()">
					返回
				</div>
				<div class="custom-bar-center">
					{{ title }}
				</div>
				<view></view>
			</slot>
		</div>
		<uni-drawer ref="drawer">
			<Drawer @close="closeDrawer()"/>
		</uni-drawer>
	</view>
</template>

<script>
	import Drawer from '../Drawer.vue'
	import UniDrawer from '../uni-drawer/uni-drawer.vue'
	export default {
		components: {
			Drawer,
			UniDrawer
		},
		props: {
			mode: {
				type: String,
				default: 'menu'
			},
			title: String
		},
		data() {
			return {
				show: false,
				statusBar: this.statusBar,
				customBar:this.customBar
			};
		},
		created() {
			// console.log(this.statusBar, this.customBar)
		},
		methods: {
			openDrawer() {
				this.$refs['drawer'].open()
			},
			closeDrawer() {
				this.$refs['drawer'].close()
			},
			back() {
				uni.navigateBack()
			}
		}
	}
</script>

<style lang="scss">
.navbar {
	color: #fff;
	background: linear-gradient(45deg, $uni-color-blue, $uni-color-purle);
}
.custom-bar {
	padding: 0 30rpx;
	display: flex;
	align-items: center;
	justify-content: space-between;
}
</style>
