<template>
	<view>
		this is a comp<button @click="addNum" type="default">update b comp</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num:0 
			};
		},
		methods:{
			addNum(){
					uni.$emit('updateNum',10)
			}
		}
	}
</script>

<style>

</style>
