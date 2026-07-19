<template>
	<view class="container">
		<view class="group">
			<view class="title" style="background-color:orangered;">
				<text>动作片</text>
			</view>
			<movie></movie>
		</view>
		<view class="group">
			<view class="title" style="background-color:hotpink;">
				<text>爱情片</text>
			</view>
			<movie02></movie02>
		</view>
		<view class="group">
			<view class="title" style="background-color:green;">
				<text>爱情片</text>
			</view>
			<movie03></movie03>
		</view>
		<view class="group">
			<view class="title" style="background-color:black;">
				<text>恐怖片</text>
			</view>
			<movie04></movie04>
		</view>
		<view class="group">
			<view class="title" style="background-color:mediumpurple;">
				<text>悬疑片</text>
			</view>
			<movie05></movie05>
		</view>
		<view class="group">
			<view class="title" style="background-color:red">
				<text>惊悚片</text>
			</view>
			<movie06></movie06>
		</view>
	</view>
</template>

<script setup>
	import {ref} from 'vue'
	import movie from '@/movieList/movie.vue'
	import movie02 from '@/movieList/movie02.vue'
	import movie03 from '@/movieList/movie03.vue'
	import movie04 from '@/movieList/movie04.vue'
	import movie05 from '@/movieList/movie05.vue'
	import movie06 from '@/movieList/movie06.vue'
	
	let movieList = [
		[
			{
				
			}
		]
	]
</script>

<style scoped>
	.container{
		width:100%;
		height:500rpx;
	}
	.container .group{
		width:100%;
		height:500rpx;
		margin-bottom:20rpx;
		/* border:2rpx solid red; */
	}
	.container .title{
		width:100%;
		height:80rpx;
		background-color:orangered;
		text-align:center;
	}
	.container .title text{
		line-height:80rpx;
		color:white;
		font-size:36rpx;
	}
</style>
