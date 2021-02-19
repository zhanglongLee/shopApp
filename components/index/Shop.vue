<template>
	<view class="shop">
		<view class="shop-item">
			<image class="shop-big" src="../../static/img/shop.jpg" mode=""></image>
			<scroll-view scroll-x="true" class="scroll-content">
				<view class="scroll-item">
					<commodity
						:dataList="shopList"
						bigW="200rpx"
						bigH="200rpx"
						wrap="no-wrap"
						nameSize="26rpx"></commodity>
				</view>
			</scroll-view>
		</view>
		<view class="shop-item">
			<image class="shop-big" src="../../static/img/shop.jpg" mode=""></image>
			<scroll-view scroll-x="true" class="scroll-content">
				<view class="scroll-item">
					<commodity
						:dataList="shopList"
						bigW="200rpx"
						bigH="200rpx"
						wrap="no-wrap"
						nameSize="26rpx"></commodity>
				</view>
			</scroll-view>
		</view>
	</view>
</template>

<script>
	import commodity from '../common/commodity.vue'
	export default{
		data(){
			return{
				shopList:[
					{
						id:1,
						imgUrl:"../../static/img/shop1.jpg",
						name:"春节爆款春节爆款春节爆款春节爆款春节爆款春节爆款春节爆款春节爆款春节爆款",
						pprice:"299",
						oprice:"655",
						discount:"5.2"
					},
					{
						id:2,
						imgUrl:"../../static/img/shop2.jpg",
						name:"连衣裙爆款连衣裙爆款连衣裙爆款连衣裙爆款连衣裙爆款连衣裙爆款",
						pprice:"199",
						oprice:"499",
						discount:"5.2"
					},
					{
						id:3,
						imgUrl:"../../static/img/shop3.jpg",
						name:"冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款",
						pprice:"199",
						oprice:"499",
						discount:"5.2"
					},
					{
						id:4,
						imgUrl:"../../static/img/shop4.jpg",
						name:"帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备",
						pprice:"199",
						oprice:"499",
						discount:"5.2"
					},
					{
						id:2,
						imgUrl:"../../static/img/shop2.jpg",
						name:"连衣裙爆款连衣裙爆款连衣裙爆款连衣裙爆款连衣裙爆款连衣裙爆款",
						pprice:"199",
						oprice:"499",
						discount:"5.2"
					},
					{
						id:3,
						imgUrl:"../../static/img/shop3.jpg",
						name:"冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款",
						pprice:"199",
						oprice:"499",
						discount:"5.2"
					},
					{
						id:4,
						imgUrl:"../../static/img/shop4.jpg",
						name:"帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备",
						pprice:"199",
						oprice:"499",
						discount:"5.2"
					}
				]
			}
		},
		components:{
			commodity
		}
	}
</script>

<style scoped>
	
	.scroll-content{
		width: 100%;
	}
	.scroll-item{
		display: inline-block;
	}
	.shop-big{
		display: block;
		width: 100%;
		height: 340rpx;
	}
</style>
