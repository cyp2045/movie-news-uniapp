<template>
	<view class="banner-bg" :style="`background-image: linear-gradient(to bottom, ${bannerBg[current].bgcolor}, white)`">
		<view class="banner-box">
			<swiper 
			:indicator-dots="true" 
			:autoplay="true" 
			:interval="3000" 
			:duration="1000"
			:circular="true"
			indicator-active-color="#007aff"
			 @change="swiperChange"
			>
				<swiper-item v-for="(item,index) in bannerList" :key="index">
					<image :src="item.url"></image>
				</swiper-item>
			</swiper>
		</view>
	</view>
</template>

<script setup>
	import {ref} from 'vue'
	import { bannerList,bannerBg } from "@/common/data/data.js"
	let current = ref(0)
	
	// 轮播切换时更新 current
	const swiperChange = (e) => {
	    current.value = e.detail.current
	}
</script>

<style scoped>
	.banner-bg{
		width:100%;
		height:360rpx;
		position:relative;
	}
	.banner-bg .banner-box{
		width:80%;
		height:300rpx;
		border-radius:15rpx;
		/* border:2rpx solid black; */
		position:absolute;
		bottom:0%;
		left:10%;
	}
	.banner-bg .banner-box swiper{
		width:100%;
		height:100%;
		border-radius:15rpx;
		/* border:2rpx solid black; */
	}
	.banner-bg .banner-box swiper image{
		width:100%;
		height:100%;
		border-radius:15rpx;
	}
	
	
	@media (min-width:961px) {
			.banner-bg{
				height:860rpx;
			}
			.banner-bg .banner-box{
				height:800rpx;
			}
		}
		@media (min-width:1300px) {
			.banner-bg{
				height:1560rpx;
			}
			.banner-bg .banner-box{
				height:1400rpx;
			}
		}
	
</style>