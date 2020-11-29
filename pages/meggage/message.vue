<template>
	<view>
		<button type="primary" @click="chooseImage"> upload image </button>
		<image v-for="item in imgArr" :src="item" @click="previewImage(item)"></image>
	<!--#ifdef H5 -->
	<view>  i hope look  at  h5 page</view>
	<!--#endif  -->
		<!--#ifdef MP-WEIXIN -->
	<view>  i hope look  at  wechat little programmer page</view>
	<!--#endif  -->	
	</view>
</template>

<script>
	export default {
		data() {
			return {
				imgArr:[]
			}
		},
		methods: {
			chooseImage(){
				console.log('choose image')
				uni.chooseImage({
					count:5,
					success:res => {
						console.log(res)
						this.imgArr = res.tempFilePaths
					}
				})
			},
			previewImage(current){
				uni.previewImage({ 	
					current:current,
					urls:this.imgArr,
					loop:true,
					indicator:'number'
				})
			}
		
			
		},
	onLoad(){
		//#ifdef H5
				console.log('i hjope h5 print')
				//#endif
				//#ifdef MP-WEIXIN
				console.log('i hjope wechat print')
				//#endif
			}
	}	
	
</script>

<style>
/*h5*/
/* #ifdef H5 */
view{
	color: #F0AD4E;	
}
/*#endif*/
/*wechat 条件注释 实现跨段兼容*/
/* #ifdef MP-WEIXIN */
view{
	color: #DD524D;
}
/*#endif */
</style>
