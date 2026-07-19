<template>
	<view class="container">
		<uni-list>
			<uni-list-item 
			:title="item.title" 
			:note="item.author_name"
			:thumb="item.cover"
			thumbSize="lg"
			v-for="(item,index) in notes"
			:key="index"
			link="navigateTo"
			:to="'/pages/info/info?id='+item.post_id"
			>
			</uni-list-item>
		</uni-list>
	</view>
</template>

<script setup>
	// 当页面载入完成后获取请求
	import {onLoad} from '@dcloudio/uni-app'
	import {ref} from 'vue'
	let notes = ref(null)
	onLoad(
		uni.request({
			url:'https://unidemo.dcloud.net.cn/api/news',
			method:'GET',
			success: (res) => {
				console.log(res.data)
				notes.value = res.data
			}
		})
	)
</script>

<style></style>
