<template>
<!-- 	<view>
		<view>
		detail page
		<text selectable="true" space="emsp" decode="false"> sing dance  play basketball</text>
		<text selectable="true" space="ensp" decode="false"> detail  </text>
	</view>
	<view>
		
		<text selectable="true" space="emsp" decode="false"> sing dance 2  play basketball</text>
		<text selectable="true" space="ensp" decode="false" style="font-size: 100sp;"> detailssss2</text>
	</view>
	</view> --> 
	
<view class="box2" hover-class="box2-active">
	<view class="box" hover-class="box-active" :hover-start-time="2000" :hover-stay-time="2000">  阻止此节点祖先节点相应事件this is a big  view</view>
	 <view class="box3 " hover-class="box3-active" > this is a 3 box</view>、
	 <button type="warn">btn</button>
	 <button type="default" plain="true" disabled="true">btn</button>
	 <button size="mini" type="primary"> btn2</button>
	 <button type="warn" loading>btnddd</button>
	 <image src="../../../static/logo.png" mode="aspectFill" ></image>
	 <image src="../../../static/logo.png" mode="aspectFit"></image>
	 	 <image src="../../../static/logo.png" ></image>
	 <button type="warn">btn</button>
	 </view>
</template>

<script>
	export default {
		onLoad(options) {
			console.log(options)
		},
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style>

.box{
	width: 200rpx;
	height: 200rpx;
	background-color: #007AFF;
}
.box2{
	width: 400rpx;
	height: 400rpx;
	background-color: #8F8F94;
}
.box3{
    width: 400rpx;
	height: 400rpx;
	background-color: #8F8F94	
}
.box-active{
	background-color: #DD524D; 
}
.box2-active{
	background-color: #555555;
}
.box3-active{
	background-color: #F0AD4E;
}
</style>
