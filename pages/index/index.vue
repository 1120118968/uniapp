<template>
	<view class="content">
		<!-- <image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title">{{title}}</text>
	
		</view>	 -->
		<test v-if="flag" :title="title" @myEvent="getNum"></test>
		<button type="default" @click="checkTest">切换test组件</button>
		This is son components give value {{num}}
		<test-a></test-a>
		<test-b></test-b>	
		<view>
		    <uni-calendar 
		    :insert="true"
		    :lunar="true" 
		    :start-date="'2020-11-29'"
		    :end-date="'2020-12-31'"
		    @change="change"
		     ></uni-calendar>
		</view>
	</view>
</template>

<script>
	import test from '../../components/test.vue'
	import testA from '../../components/a.vue'
	import testB from '../../components/b.vue'
    import uniCalendar from '@/components/uni-calendar/uni-calendar.vue'
	
	export default {
		data() {
			return {
				title: 'hhh',
				num:0,
				flag: true
			}
		},
		onLoad(options) {
			console.log('page load',options)
		},
		onShow() {
			console.log("page show")
		},
		onReady() {
			console.log("page init paint")
		},
		onHide() {
			console.log("page hide")
		},
		methods: {
			checkTest(){
				this.flag = !this.flag 
			},
			getNum(num){
				console.log(num)
				this.num = num
			},
			change(e){
				console.log('click enent',e)
			}
		},
		components:{
			test,
			"test-a":testA,
			"test-b":testB,
			uniCalendar
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
