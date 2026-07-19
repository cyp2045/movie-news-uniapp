<template>
	<view class="container">
		<view class="title">
			{{data.title}}
		</view>
		<view class="content">
			<rich-text :nodes="data.content"></rich-text>
		</view>
	</view>
</template>

<script setup>
	import {ref} from 'vue'
	import {onLoad} from '@dcloudio/uni-app'
	let data = ref({})
	onLoad(options=>{
		console.log(options.id)
		uni.request({
			url:'https://unidemo.dcloud.net.cn/api/news/36kr/'+options.id,
			method:"GET",
			success: (res) => {
				console.log(res.data)
				data.value = res.data
			}
		})
	})
</script>

<style>
	.title{
		color:red;
		font-size:48rpx;
		font-weight:bold;
	}
</style>
