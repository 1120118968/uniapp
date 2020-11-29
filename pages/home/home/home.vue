<template>
	<view>
		<view>
			data bind study
		</view>
		<view>{{msg}}</view>
		<view>{{1 + 'hello  everyone'}}</view>
		<view>{{1+1}}</view>
		<view>{{flag?'true':'false'}}</view>
		<image v-bind:src="imageUrl"></image>


<view v-for="(item,index) in arr" :key = "item.id">
	number:{{item.id}},
	name:{{item.name}},
	age:{{item.age}}
	</view>
	<button v-on:click="clickButton(200,$event)" type="primary">bbbb</button>
	</view>
</template>

<script>
	export default {
		data() {
			return {

				msg: 'hello',
				flag: true,
				imageUrl: 'https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1605000564560&di=556fbd7fb99bf22349899df6f6766b17&imgtype=0&src=http%3A%2F%2F5b0988e595225.cdn.sohucs.com%2Fimages%2F20170723%2F4ff0ef20fec84cb1b72f59df3fd120f2.jpeg',
				arr: [{
						"name": 'w',
						"age": 20,
						"id": 1
					},
					{
						"name": 'z',
						"age": 10,
						"id": 2
					},
					{
						"name": 'c',
						"age": 25,
						"id": 3
					},
					{
						"name": 'x',
						"age": 50,
						"id": 4
					}
				]

			}
		},
		methods: {
		clickButton(num,e){
			console.log('click',num,e)
		}

		}
	}
</script>

<style>

</style>
