<template>
	<view class="body">
		<swiper next-margin="60rpx">
			<swiper-item v-for="(items,index) in movieList" :key="index">
				<view class="movieBox" v-for="(item,index) in items" :key="index">
					<view class="body-top">
						<image :src="item.url" style="width:100%;height:100%;border-radius:20rpx;"></image>
					</view>
					<view class="body-bottom">
						<view class="desc">
							<text>{{item.desc}}</text>
						</view>
						<view class="info">
							<text class="date">{{item.date}}</text>
							<text class="read">{{item.read}} 阅读</text>
						</view>
					</view>
				</view>
			</swiper-item>
		</swiper>
	</view>
</template>

<script setup>
	import {ref} from 'vue'
	
	let movieList = ref(
	[
		[
			{
				id:1,
				url:'/static/images/it1.png',
				desc:'我的规矩就是规矩',
				date:'2024-05-23',
				read:'2000+'
			},
			{
				id:2,
				url:'/static/images/it2.png',
				desc:'江湖格斗家',
				date:'2024-04-13',
				read:'2450+'
			}
		],
		[
			{
				id:3,
				url:'/static/images/it3.png',
				desc:'疾速追杀:芭蕾杀姬',
				date:'2024-04-21',
				read:'2080+'
			},
			{
				id:4,
				url:'/static/images/it4.png',
				desc:'阿尔法:男人爱复仇',
				date:'2024-05-23',
				read:'2000+'
			}
		],
		[
			{
				id:5,
				url:'/static/images/it5.png',
				desc:'猎狐·行动',
				date:'2024-05-23',
				read:'2000+'
			},
			{
				id:6,
				url:'/static/images/it6.png',
				desc:'缉盗',
				date:'2024-05-23',
				read:'2000+'
			}
		]
	]
	)
</script>

<style scoped>
	
	
	.container .body{
		width:100%;
		height:420rpx;
		/* border:2rpx solid black; */
	}
	.container .body swiper{
		width:100%;
		height:100%;
	}
	.container .body swiper swiper-item{
		width:100%;
		display:flex;
		align-items:center;
		flex-shrink:0;
	}
	.container .body swiper .movieBox{
		width:300rpx;
		height:400rpx;
		background-color:#eee;
		border-radius:20rpx;
		display:flex;
		flex-direction:column;
		align-items:center;
		justify-content:space-between;
		margin:0 30rpx;
		flex-shrink: 0;
	}
	.container .body swiper .movieBox .body-top{
		width:90%;
		height:360rpx;
		margin-top:20rpx;
	}
	.container .body swiper .movieBox .body-bottom{
		width:80%;
		height:180rpx;
		margin-top:30rpx;
		/* border:2rpx solid black; */
	}
	.container .body swiper .movieBox .body-bottom .desc{
		width:100%;
		height:80rpx;
		/* border:2rpx solid black; */
		line-height: 1.5;
		font-weight:bold;
		font-size:24rpx;
		color:red;
	}
	.container .body swiper .movieBox .body-bottom .desc text{
		padding:20rpx;
		-webkit-line-clamp:2;
		overflow:hidden;
	}
	.container .body swiper .movieBox .body-bottom .info{
		display:flex;
		justify-content:space-between;
		line-height:60rpx;
		font-size:18rpx;
		color:grey;
		padding:0 10rpx;
	}
</style>
