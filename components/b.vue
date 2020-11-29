<template>
	<view>
		This is a comp b data :{{num}}
	</view>
</template>

<script>
	export default {
		data() {
			return {
				num:0
			};
		},
		created() {
			uni.$on('updateNum',num=>{
				this.num += num
			})
		}
	}
</script>

<style>

</style>
