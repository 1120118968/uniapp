<template>
	<view>
		<button @click="get">send get request</button>
		<view>list page </view>
		<button type="primary" @click="setStor"> save data</button>
		<button type="primary" @click="getStor">get data</button>
		<button type="primary" @click="removeId">remove data</button>
		<view class="box-item" v-for="item in list">{{item}} </view>
		<button @click="pullDown"> click button pull Down fresh</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				list: [
					"web", "java", "UI", "test", "big data", "web", "java", "UI", "test", "big data", "web", "java", "UI", "test",
					"big data"
				]
			}
		},
		onPullDownRefresh() {
			console.log('cf xl fresh')

			setTimeout(() => {
				// cf xlsx yc 2s
				this.list = ["UI", "test", "big data", "web", "java"]
				uni.stopPullDownRefresh()
				//close page pull down fresh
			}, 2000)
		},
		onReachBottom() {
			console.log("page bottom")
			this.list = [...this.list, ...["UI", "test", "big data", "web", "java"]]
			//bottom load next page data
		},
		methods: {
			pullDown() {
				uni.startPullDownRefresh({ //start pull down fresh

				})
			},
			get() {
				uni.request({
					url: "https://api-hmugo-web.itheima.net/api/public/v1/home/swiperdata",
					//data:
					success(res) {
						console.log(res)
					}
				})
			},
			setStor() {
				// uni.setStorage({
				// 	key: 'id',
				// 	data: 80,
				// 	success() {
				// 		console.log("successs")
				// 	}
				// }) 
			uni.setStorageSync('id',100)
			},
			getStor(){
				uni.getStorage({
					key:'id',
					success(res) {
						console.log('get success',res.data)
					}
				})
                const res = uni.getStorageSync('id')
				console.log(res)
			},
			removeId(){
				// uni.removeStorage({//同步
				// 	key:'id',
				// 	success() {
				// 		console.log('remove success')
				// 	}
				// })
				uni.removeStorageSync('id')//异步
			}
			
		}

	}
</script>

<style>
	.box-item {
		width: 100rpx;
		height: 100rpx;
	}
</style>
