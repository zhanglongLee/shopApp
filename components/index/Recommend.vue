<template>
	<view class="recommend bg-color">
		<view class="recommend-item" v-for="(item,index) in dataList" :key="index">
			<image class="img-big" :src="item.bigUrl" mode=""></image>
			<view class="img-small">
				<image 
				v-for="(k,i) in item.data" :key="i" 
				class="item-small" 
				:src="k.imgUrl" mode=""></image>
			</view>
		</view>
	</view>
</template>

<script>
	export default{
		props:{
			dataList:{
				type:Array
			}
		}
	}
</script>

<style scoped>
	.recommend{
		padding: 20rpx;
	}

	.recommend-item{
		display: flex;
		flex-direction: column;
		width: 100%;
		margin-top: 20rpx;
		border: 2rpx solid #ccc;
		border-radius: 20rpx;
		overflow: hidden;
	}
	.recommend-item:first-child{
		margin-top: 0;
	}
	.img-big{
		width: 100%;
		height: 300rpx;
	}
	.img-small{
		display: flex;
		width: 100%;
		height: 240rpx;
	}
	.item-small{
		flex: 1;
	}
</style>
