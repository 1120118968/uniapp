<template>
	<view>

<view > navigation page jump </view>	
	<navigator url="../../detail/detail/detail?id=80&age=19"> jump to detail page</navigator>
	<navigator url="../../meggage/message" open-type="switchTab"> jump to message page</navigator>
	<navigator url="../../detail/detail/detail" open-type="redirect"> jump to detail page</navigator>
	<button type="default" @click="goDetail"> jump to detail page </button>
	<button type="default" @click="goMessage"> jump to message page </button>
	<button type="default" @click="goDetail2()">jump to detail page close current page</button>
	</view>
</template>

<script>
	export default {
		onUnload() {
			console.log('navigator page uninstall')
		}, 
		data() {
			return {
				
			}
		},
		methods: {
			goDetail(){
				uni.navigateTo({
					url:"../../detail/detail/detail"
				})
			},
			goMessage(){
				uni.switchTab({
					url:"../../meggage/message"
				})
			},
			goDetail2(){
				uni.redirectTo({
			        url:"../../detail/detail/detail"
				})
			}
		}
	}
</script>

<style>

</style>
