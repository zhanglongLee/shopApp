<template>
	<view class="recommend bg-color">
		<view class="recommend-item">
			<image class="img-big" src="../../static/img/Children.jpg" mode=""></image>
			<view class="img-small">
				<image class="item-small" src="../../static/img/Children1.jpg" mode=""></image>
				<image class="item-small" src="../../static/img/Children2.jpg" mode=""></image>
				<image class="item-small" src="../../static/img/Children3.jpg" mode=""></image>
			</view>
		</view>
		<view class="recommend-item">
			<image class="img-big" src="../../static/img/Furnishing.jpg" mode=""></image>
			<view class="img-small">
				<image class="item-small" src="../../static/img/Furnishing1.jpg" mode=""></image>
				<image class="item-small" src="../../static/img/Furnishing2.jpg" mode=""></image>
				<image class="item-small" src="../../static/img/Furnishing3.jpg" mode=""></image>
			</view>
		</view>
	</view>
</template>

<script>
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
