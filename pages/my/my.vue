<template>
	<view class="container">
		<view class="header">
			<view class="header-img">
				<image src="/static/images/header.jpeg"></image>
			</view>
			<view class="header-name">
				<text>cyp2045</text>
				<text class="iconfont icon-shezhi">设置</text>
			</view>
		</view>
		<view class="body">
			<view class="body-item" v-for="(item,index) in bodyItem" :key="index">
				<view class="left">
					<text class="iconfont" :class="item.icon">&nbsp;&nbsp;{{item.text}}</text>
				</view>
				<text class="iconfont icon-qiehuanzhanghu"></text>
			</view>
		</view>
		<view class="footer">
			<text>退 出 登 录</text>
		</view>
	</view>
</template>

<script setup>
	let bodyItem = [
		{
			id:1,
			icon:'icon-qiandao',
			text:'签到'
		},
		{
			id:2,
			icon:'icon-shoucang',
			text:'收藏阁'
		},
		{
			id:3,
			icon:'icon-lishijilu',
			text:'历史记录'
		},
		{
			id:4,
			icon:'icon-huiyuan',
			text:'会员中心'
		}
	]
</script>

<style scoped>
	 .container{
		 width:100%;
		 height:1150rpx;
		 /* border:2rpx solid black; */
		 background-color:#eee;
		 display:flex;
		 flex-direction:column;
		 align-items:center;
	 }
	 .header{
		 width:96%;
		 height:240rpx;
		 background-color:white;
		 display:flex;
		 justify-content:space-evenly;
		 align-items:center;
	 }
	 .header .header-img{
		 width:160rpx;
		 height:160rpx;
	 }
	 .header .header-img image{
		 width:100%;
		 height:100%;
		 border-radius:50%;
	 }
	 .header .header-name{
		 width:300rpx;
		 height:200rpx;
		 /* border:2rpx solid black; */
		 display:flex;
		 flex-direction:column;
		 justify-content:space-around;
		 padding:0 20rpx;
	 }
	 .header .header-name text:first-child{
		 font-size:48rpx;
		 font-weight:bold;
	 }
	 .header .header-name text:last-child{
		 font-size:36rpx;
		 color:darkgrey;
	 }
	 
	 .body{
		 width:96%;
		 height:600rpx;
	 }
	 .body .body-item{
		 width:100%;
		 height:120rpx;
		 background-color:white;
		 margin:20rpx 0;
		 display:flex;
		 align-items:center;
		 padding:0 60rpx;
		 justify-content:space-between;
	 }
	 .body .body-item .left .iconfont{
		 font-size:36rpx;
	 }
	 .body .body-item .iconfont.icon-qiehuanzhanghu{
		 color:darkgrey;
	 }
	 
	 .footer{
		 width:90%;
		 height:100rpx;
		 background-color:red;
		 border-radius:50rpx;
		 text-align:center;
	 }
	 .footer text{
		 line-height:100rpx;
		 font-size:36rpx;
		 color:white;
	 }
</style>
