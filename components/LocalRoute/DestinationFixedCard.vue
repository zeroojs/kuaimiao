<template>
	<cover-view class="destination-fixed-card cover-view-card">
		<cover-view class="destination-fixed-card-title">
			FAVOURITES DESTINATION
		</cover-view>
		<cover-view class="destination-fixed-card-group">
			<cover-view
				v-for="item in destinations.favourites"
				:key="item.id"
				:class="['destination-fixed-card-item', item.tag]">
				<cover-image class="icon icon-homne" :src="item.icon"></cover-image>
				<cover-view>{{ item.target }}</cover-view>
			</cover-view>
			<!-- <cover-view class="destination-fixed-card-item office">
				<cover-image class="icon icon-office" src="../../static/icon/office.svg"></cover-image>
				<cover-view>My Office</cover-view>
			</cover-view> -->
		</cover-view>
		<cover-view class="destination-fixed-card-group search">
			<cover-view
				v-for="item in destinations.recommend"
				:key="item.id"
				:class="['destination-fixed-card-item', { active: item.active }]"
				@click="selectTarget(item)">
				<cover-image 
					class="icon icon-local-gray" 
					:src="`../../static/icon/${item.active ? 'local' : 'local-gray'}.svg`"></cover-image>
				<cover-view>{{ item.target }}</cover-view>
			</cover-view>
			<!-- <cover-view class="destination-fixed-card-item active">
				<cover-image class="icon icon-local-gray" src="../../static/icon/local.svg"></cover-image>
				<cover-view>Harvard University</cover-view>
			</cover-view>
			<cover-view class="destination-fixed-card-item">
				<cover-image class="icon icon-local-gray" src="../../static/icon/local-gray.svg"></cover-image>
				<cover-view>Aristy University</cover-view>
			</cover-view>
			<cover-view class="destination-fixed-card-item">
				<cover-image class="icon icon-local-gray" src="../../static/icon/local-gray.svg"></cover-image>
				<cover-view>University of Lounge Farm</cover-view>
			</cover-view> -->
		</cover-view>
	</cover-view>
</template>

<script>
	const destinations = {
		favourites: [
			{
				id: 'fav-1',
				tag: 'home',
				icon: '../../static/icon/home.svg',
				target: 'Home'
			},
			{
				id: 'fav-2',
				tag: 'office',
				icon: '../../static/icon/office.svg',
				target: 'My Office'
			}
		],
		recommend: [
			{
				id: 'rec-1',
				active: false,
				target: 'University of Cambridge'
			},
			{
				id: 'rec-2',
				active: true,
				target: 'Harvard University'
			},
			{
				id: 'rec-3',
				active: false,
				target: 'Aristy University'
			},
			{
				id: 'rec-4',
				active: false,
				target: 'University of Lounge Farm'
			},
		]
	}
	export default {
		data() {
			return {
				target: {},
				destinations
			};
		},
		methods: {
			selectTarget(item) {
				this.target = item;
				this.$emit('handleChangeTarget', item.target);
				this.$emit('showChooseCar')
			}
		}
	}
</script>

<style lang="scss">
$border: 1rpx solid #FAFAFA;
.icon {
	width: 36rpx;
	height: 36rpx;
	margin-right: 30rpx;
}
.destination-fixed-card {
	margin-top: 30rpx;
	transform: unset;
	height: auto;
	font-weight: 500;
	color: #8A8A8A;
	padding-left: 0;
	padding-right: 0;
}
.destination-fixed-card-title {
	padding: 30rpx;
	border-bottom: $border;
}
.destination-fixed-card-item {
	display: flex;
	align-items: center;
	width: 100%;
	height: 80rpx;
	padding: 0 30rpx;
	&.home {
		color: #DEAC21;
	}
	&.office {
		color: #FF6833;
	}
	&.active {
		color: $uni-color-purle;
		background-color: #F5F3F9;
	}
}
.destination-fixed-card-group {
	padding-bottom: 30rpx;
	&.search {
		padding-top: 30rpx;
		border-top: $border;
		padding-bottom: 0;
	}
}
</style>
