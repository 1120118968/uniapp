<template>
	<view id="myView">
		This is a test components {{num}} 
		This is a parent components msg {{title}}
		<button type="default" @click="giveValue()">give value parent components</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num:3,
				intId:null
			};
		},
		props:['title'],
		methods:{
			giveValue(){
				console.log('give paren componets value')
				this.$emit('myEvent',this.num)
			}
		}, 
		beforeCreate() {
			console.log('beforeCreate 实例已经开始初始化')
		    console.log(this.num)
		},
		created() {
			console.log('created 实例创建完成')
			console.log(this.num)
			console.log('created 实例创建完成',this.num)
			// this.intId = setInterval(()=>{
			// 	console.log('执行定时器')
			// },1000)
		},
		beforeMount(){
			// console.log('beforeMount',document.getElementById('myView'))
		},
		mounted() {
			// console.log('mounted',document.getElementById('myView'))
		},
		destroyed() {
			console.log('组件销毁了')
			clearInterval(this.intId)
		}

	}
</script>

<style>

</style>
