<template>
	<view class="nav">
		<view class="search">
			<text class="iconfont icon-sousuo"></text>
			<input type="text" placeholder="请输入关键词..."/>
		</view>
		<view class="menu">
			<view class="iconfont icon-caidan"  @click="menuIcon">
				<view class="ul-menu" v-show="isMenuOpen">
					<text>热门电影</text>
					<text>韩国爽剧</text>
					<text>热榜小说</text>
					<text>虐心短剧</text>
					<text>我的中心</text>
				</view>
			</view>
		</view>
	</view>
	<view class="nav02">
		<view class="navBox">
			<text v-for="(item,index) in navList">{{item.text}}</text>
		</view>
	</view>
</template>

<script setup>
	import {onMounted, ref} from 'vue'
	import { navList } from "@/common/data/data.js"
	
	let isMenuOpen = ref(false)
	const menuIcon = () => {
		isMenuOpen.value = !isMenuOpen.value
	}
</script>

<style scoped>
	/* 第一种布局 */
	.nav{
		width:100%;
		height:100rpx;
		/* border:2rpx solid black; */
		margin:20rpx auto;
		background-color:rgba(0,0,0,0.8);
		display:flex;
		align-items:center;
		justify-content:space-between;
		padding:0 50rpx;
	}
	.nav .search{
		width:80%;
		height:60rpx;
		border:2rpx solid white;
		border-radius:20rpx;
		color:white;
		padding:0 20rpx;
		display:flex;
		align-items:center;
	}
	.nav .search .iconfont.icon-sousuo{
		font-size:25rpx;
	}
	.nav .search input{
		width:100%;
		height:60rpx;
		padding-left:20rpx;
		font-size:24rpx;
	}
	/* 菜单 */
	.nav .menu{
		width:60rpx;
		height:60rpx;
		/* border:2rpx solid black; */
		display:flex;
		justify-content:center;
		align-items:center;
	}
	.nav .menu .iconfont{
		font-size:50rpx;
		color:white;
		position:relative;
	}
	/* 二级菜单 */
	.nav .menu .iconfont .ul-menu{
		width:160rpx;
		height:400rpx;
		background-color:rgba(0,0,0,0.8);
		display:flex;
		flex-direction: column;
		position:absolute;
		top:75rpx;
		right:-54rpx;
		z-index:999;
		/* display:none; */
		animation:all 0.3s ease;
	}
	.nav .menu .iconfont .ul-menu text{
		width:160rpx;
		height:80rpx;
		font-size:25rpx;
		text-align:center;
		line-height:80rpx;
		animation:all 0.3s ease;
	}
	.nav .menu .iconfont .ul-menu text:hover{
		color:yellow;
		transform:scale(1.1);
	}
	/* 第二种布局 */
	.nav02{
		width:100%;
		height:200rpx;
		display:flex;
		margin:20rpx auto;
		background-color:rgba(0,0,0,0.8);
		display:flex;
		align-items:center;
		justify-content:center;
	}
	.nav02 .navBox{
		width:100%;
		height:180rpx;
		/* border:2rpx solid white; */
		display:flex;
		align-items:center;
	}
	.nav02 .navBox text{
		flex:1;
		color:white;
		font-size:48rpx;
		text-align:center;
		transition:all 0.3s ease;
	}
	.nav02 .navBox text:hover{
		transform:scale(1.2);
		color:yellow;
	}
	
	
	@media (min-width:367px) {
			.nav{
				display:flex;
			}
			.nav02{
				display:none;
			}
		}
		@media (min-width:961px) {
			.nav{
				display:none;
			}
			.nav02{
				display:flex;
			}
		}
		@media (min-width:1300px) {
			.nav{
				display:none;
			}
			.nav02{
				display:flex;
			}
		}
</style>