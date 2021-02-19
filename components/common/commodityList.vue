<template>
	<view class="commodity-list">
		<!-- 猜你喜欢商品列表 -->
		<commodity :dataList="commodityList"></commodity>
	</view>
</template>

<script>
	import commodity from './commodity.vue'
	export default{
		components:{
			commodity
		},
		data(){
			return{
				commodityList:[
					{
						id:1,
						imgUrl:"../../static/img/commodity1.jpg",
						name:"春节爆款春节爆款春节爆款春节爆款春节爆款春节爆款春节爆款春节爆款春节爆款",
						pprice:"299",
						oprice:"655",
						discount:"5.2"
					},
					{
						id:2,
						imgUrl:"../../static/img/commodity2.jpg",
						name:"连衣裙爆款连衣裙爆款连衣裙爆款连衣裙爆款连衣裙爆款连衣裙爆款",
						pprice:"199",
						oprice:"499",
						discount:"5.2"
					},
					{
						id:3,
						imgUrl:"../../static/img/commodity3.jpg",
						name:"冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款冬季爆款",
						pprice:"199",
						oprice:"499",
						discount:"5.2"
					},
					{
						id:4,
						imgUrl:"../../static/img/commodity4.jpg",
						name:"帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备帅哥必备",
						pprice:"199",
						oprice:"499",
						discount:"5.2"
					}
				]
			}
		}
	}
</script>

<style>
</style>
