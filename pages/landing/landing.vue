<template>
	<view class="landing">
		<div class="landing-bg landing-bg-top linear-bg"></div>
		<div class="landing-bg landing-bg-bottom"></div>
		<Overview v-if="showGroup.overview"></Overview>
		<SignIn
			v-if="showGroup.signIn"
			class="landing-item sign-in"
		></SignIn>
		<SignUp 
			v-if="showGroup.signUp"
			class="landing-item sign-up"
			@showController="showController"
		></SignUp>
		<EnterCode v-if="showGroup.enterCode" class="landing-item sign-up"></EnterCode>
		<VerifyStep
			v-if="showGroup.verifyStep"
			class="landing-item verify-step"
			@showController="showController"/>
		<view v-if="showGroup.signUp || showGroup.verifyStep" class="sign-up-tips">
			<text>Already have account ?</text>
			<text @click="showController('signIn')" class="link">Sign In</text>
		</view>
		<view v-else class="sign-in-tips">
			<text>Don’t have account ?</text>
			<text @click="showController('signUp')" class="link">Sign Up</text>
		</view>
	</view>
</template>

<script>
	import SignIn  from '../../components/SignIn.vue'
	import SignUp  from '../../components/SignUp.vue'
	import EnterCode  from '../../components/EnterCode.vue'
	import VerifyStep  from '../../components/VerifyStep.vue'
	import Overview from '../../components/Overview.vue'
	export default {
		components: {
			SignIn,
			SignUp,
			Overview,
			EnterCode,
			VerifyStep
		},
		data() {
			return {
				showGroup: {
					overview: true,
					signIn: false,
					signUp: false,
					enterCode: false,
					verifyStep: false
				}
			};
		},
		methods: {
			showController(name, show = true) {
				let showGroup = this.showGroup
				for (let key in showGroup) {
					if (showGroup.hasOwnProperty(key)) {
						showGroup[key] = key === name ? show : false
					}
				}
				this.showGroup = showGroup
			}
		}
	}
</script>

<style scoped lang="scss">
.landing {
	position: relative;
	height: 100vh;
}
.landing-bg {
	height: 50vh;
	width: 100vw;
	position: absolute;
	top: 0;
	left: 0;
	z-index: -1;
}
.landing-bg-bottom {
	top: auto;
	top: 50vh;
	background-color: #fff;
}
.sign-up-tips,
.sign-in-tips {
	width: 100%;
	text-align: center;
	color: #777;
	margin-top: 24px;
	position: absolute;
	z-index: 0;
	left: 0;
	bottom: 108rpx;
	.link {
		color: $uni-color-purle;
		margin-left: 20rpx;
	}
}
.sign-in,
.sign-up,
.verify-step {
	position: absolute;
	top: 40rpx;
}
.verify-step {
	top: auto;
	bottom: 98rpx * 2;
}
</style>
