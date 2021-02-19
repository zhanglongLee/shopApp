<template>
	<view class="commodity" :style="{flexWrap:wrap}">
		<view class="commodity-item" :style="{width:bigW}" v-for="(item,index) in dataList" :key="index">
			<image class="commodity-img" :style="{height:bigH}" :src="item.imgUrl" mode=""></image>
			<view class="commodity-content">
				<text class="commodity-name" :style="{fontSize:nameSize}">{{item.name}}</text>
				<view>
					<text class="pprice">￥{{item.pprice}}</text>
					<text class="oprice">￥{{item.oprice}}</text>
				</view>
				<text class="discount">{{item.discount}}折</text>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		props:{
			dataList:{
				type:Array
			},
			bigW:{
				type:String,
				default:"375rpx"
			},
			bigH:{
				type:String,
				default:"375rpx"
			},
			wrap:{
				type:String,
				default:"wrap"
			},
			nameSize:{
				type:String,
				default:"32rpx"
			}
		}
	}
</script>

<style scoped>
.commodity{
	width: 100%;
	display: flex;
}
.commodity-item{
	margin-bottom: 20rpx;
}
.commodity-img{
	width: 100%;
}
.commodity-content{
	text-align: center;
}
.commodity-name{
	overflow: hidden;
	text-overflow: ellipsis;
	display: -webkit-box;
	-webkit-line-clamp:2;
	-webkit-box-orient: vertical;
	color: #333333;
	word-break: break-all;
	padding: 4rpx 20rpx;
}
.pprice{
	font-weight: bold;
}
.oprice{
	text-decoration: line-through;
	font-size: 24rpx;
	color: #999999;
}
.discount{
	border-radius: 4rpx;
	padding: 2rpx 10rpx;
	font-size: 20rpx;
	border: 1px solid #FF3333;
	color: #FF3333;
}
</style>
