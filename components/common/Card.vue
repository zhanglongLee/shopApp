<template>
	<view class="card-container">
		<view class="card-title">
			<view>-</view>
			<view class="card-name">{{carName}}</view>
			<view>-</view>
		</view>
		<slot>
			
		</slot>
	</view>
</template>

<script>
	export default{
		data(){
			return{
				
			}
		},
		props:{
			carName:{
				type:String
			}
		}
	}
</script>

<style scoped>
	.card-container{
		width: 100%;
	}
	.card-title{
		width: 100%;
		display: flex;
		justify-content: center;
		font-weight: bold;
		margin: 20rpx 0;
	}
	.card-name{
		font-size: 32rpx;
		padding: 0 20rpx;
	}
</style>
