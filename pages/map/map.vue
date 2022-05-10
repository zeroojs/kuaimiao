<template>
	<view class="map-page">
		<Navbar title="Home"/>
		<!-- <Drawer></Drawer>	 -->
		<uni-popup ref="popup">
			<BookSuccess
				v-if="showGroup.bookSuccess"
				@done="contactDriver"></BookSuccess>
			<RatedDriver v-if="showGroup.ratedDriver"></RatedDriver>
		</uni-popup>
		<map
			class="map"
			:scale="10"
 			:include-points="markers"
			:markers="markers"
			:latitude="latitude"
			:longitude="longitude"
		>
			<cover-view class="cover-view-container">
				<LocalInitInput
					v-if="showGroup.localInitInput"
					@showController="showController"/>
				<LocalInput
					v-if="showGroup.localInput"
					:value="inputData.target"
					@handleChangeTarget="handleChangeTarget"/>
				<DestinationFixedCard
					v-if="showGroup.destination"
					@showChooseCar="showChooseCar"
					@handleChangeTarget="handleChangeTarget"/>
				<ChooseCarFixedCard
					v-if="showGroup.chooseCar"
					@showApply="showApply"
				/>
				<PromoCodeCard
					v-if="showGroup.promoCode"
					:disabled="promoCodeDisable"
					@showController="showController"
				/>
				<!-- 					v-if="showGroup.driver" -->
				<DriverFixedCar
					v-if="showGroup.driver"
					:contact="isContact"
					@booking="booking"
					@showController="showController"
				/>
			</cover-view>
		</map>
	</view>
</template>
 
<script>
	import Navbar from '@/components/Navbar/Navbar.vue'
	import FixedCard from '@/components/FixedCard.vue'
	import LocalInput from '@/components/LocalRoute/LocalInput.vue'
	import BookSuccess from '@/components/LocalRoute/BookSuccess.vue'
	import RatedDriver from '@/components/LocalRoute/RatedDriver.vue'
	import PromoCodeCard from '@/components/LocalRoute/PromoCodeCard.vue'
	import LocalInitInput from '@/components/LocalRoute/LocalInitInput.vue'
	import DriverFixedCar from '@/components/LocalRoute/DriverFixedCar.vue'
	import ChooseCarFixedCard from '@/components/LocalRoute/ChooseCarFixedCard.vue'
	import DestinationFixedCard from '@/components/LocalRoute/DestinationFixedCard.vue'
	
	const showGroup = {
		localInitInput: true,
		localInput: false,
		promoCode: false,
		driver: false,
		chooseCar: false,
		destination: false
	}
	
	const inputData = {
		target: ''
	}
	const markers = [
		{
			id: 'self',
			latitude: 30.5702,
			longitude: 104.06476,
			iconPath: '../../static/icon/current-local.svg'
		}
	]
	
	export default {
		components: {
			Navbar,
			FixedCard,
			LocalInput,
			RatedDriver,
			BookSuccess,
			PromoCodeCard,
			DriverFixedCar,
			LocalInitInput,
			ChooseCarFixedCard,
			DestinationFixedCard
		},
		data() {
			return {
				latitude: 30.5702,
				longitude: 104.06476,
				markers,
				showGroup: {
					localInitInput: true,
					localInput: false,
					promoCode: false,
					driver: false,
					chooseCar: false,
					destination: false,
					bookSuccess: false,
					ratedDriver: false
				},
				inputData,
				isContact: false,
				promoCodeDisable: false
			};
		},
		created() {
			this.getLocation()
		},
		mounted() {
			// this.$refs.popup.open()
		},
		methods: {
			getLocation,
			showController: function(name, action = true) {
				return showController(this.showGroup, name, action)
			},
			handleChangeTarget(val) {
				this.inputData.target = val
			},
			showChooseCar() {
				this.showGroup.destination = false;
				this.showGroup.chooseCar = true;
			},
			showApply() { // 显示支付页面
				this.promoCodeDisable = true
				this.showController('localInput,promoCode')
			},
			booking() { // 预定
				this.showController('localInput,driver,bookSuccess')
				this.$refs.popup.open()
			},
			contactDriver(){ // 联系司机
				this.$refs.popup.close()
				this.isContact = true
				this.showController('localInput,driver')
			}
		},
		watch: {
			'inputData.target': function (val) {
				//  && this.showGroup.chooseCar 
				this.showGroup.destination = Boolean(val) && !this.showGroup.chooseCar 
			}
		}
	}
	// 获取坐标
	function getLocation() {
		const _this = this
		uni.getLocation({
			type: 'gcj02',
			success(res) {
				_this.latitude = res.latitude
				_this.longitude = res.longitude
				_this.markers = [
					{
						id: 'self',
						latitude: res.latitude,
						longitude: res.longitude,
						width: 60,
						height: 60,
						iconPath: '../../static/icon/current-local.svg'
					},
					...setAroundCarMarks(res.latitude, res.longitude, 4)
				]
			}
		})
	}
	// 设置附加的车辆marks
	function setAroundCarMarks(latitude, longitude, num) {
		const carMarkers = []
		for (let i = 0; i < num; i++) {
			const randLatitude = i % 2 === 0 ? (i + 1) * 0.005 : -((i + 1) * 0.005)
			const randLongitude = i > 1 ? -((i + 1) * 0.005) : (i + 1) * 0.005
			carMarkers.push({
				id: `car_${i}`,
				latitude: latitude + randLatitude,
				longitude: longitude + randLongitude,
				iconPath: '../../static/icon/map-car.svg'
			})
		}
		return carMarkers
	}
	// 显示控制
	function showController(sg, name, action) {
		name = name.split(',')
		for (let key in sg) {
			if (sg.hasOwnProperty(key)) {
				sg[key] = name.includes(key) ? action : false
			}
		}
	}
</script>

<style lang="scss">
.map {
	width: 100vw;
	height: 100vh;
}
.cover-view-container {
	padding: 40rpx 30rpx 0;
}
</style>
