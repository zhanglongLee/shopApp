<template>
	<view class="commodity-list">
		<!-- 猜你喜欢商品列表 -->
		<commodity :dataList="dataList"></commodity>
	</view>
</template>

<script>
	import commodity from './commodity.vue'
	export default{
		components:{
			commodity
		},
		props:{
			dataList:{
				type:Array
			}
		}
		
	}
</script>

<style>
</style>
