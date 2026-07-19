<template>
	<view class="container" :key="index">
		<navigator :url="item.url" open-type="navigate" v-for="(item,index) in cardList" :key="index">
			<uni-card :title="item.title" extra="更多>">
				<uni-row>
					<uni-col span="9" style="padding-right:20rpx;">
						<image :src="item.img" mode="widthFix"></image>
					</uni-col>
					<uni-col span="15">
						<view class="card-right">
							<view class="card-top" style="font-size:28rpx;line-height:1.5">
								<text class='desc'>
									{{item.desc}}
								</text>
							</view>
							<view class="card-bottom">
								<text class="read">{{item.read}} 浏览</text>
							</view>
						</view>
					</uni-col>
				</uni-row>
			</uni-card>
		</navigator>
	</view>
</template>

<script setup>
	import {cardList} from '@/common/data/data.js'
</script>

<style scoped>
	.container{
		width:100%;
		height:auto;
		margin:20rpx auto;
	}
	.container image{
		width:100%;
		height:100%;
		margin-right:20rpx;
	}
	.container uni-col:nth:nth-child(2) .card-right{
		display:flex;
		flex-direction:column;
	}
	.container .card-top .desc{
		-webkit-line-clamp:3;
		overflow:hidden;
		text-overflow:ellipsis;
		display:-webkit-box;
		-webkit-box-orient:vertical;
	}
	.container .card-bottom{
		margin-top:50rpx;
		font-size:20rpx;
		color:darkgrey;
		display:flex;
		flex-direction:row-reverse;
	}
	
	@media (min-width:961px) {
		.container .card-top .desc{
			font-size:48rpx;
		}
		.container .card-bottom{
			display:none;
		}	
	}
	@media (min-width:1300px) {
		
		.container .card-top .desc{
			font-size:48rpx;
			margin-right:50rpx;
		}
		.container .card-bottom{
			display:none;
		}		
		
	}
</style>