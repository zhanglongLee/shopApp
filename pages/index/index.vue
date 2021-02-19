<template>
	<view class="content">
		<!-- #ifdef MP-WEIXIN -->
		<Header></Header>
		<!-- #endif -->
		
		<!-- 顶部滑动导航 -->
		<scroll-view scroll-x="true" class="scroll-content" :scroll-into-view="scrollIntoIndex">
			<view 
				:id="'top'+index"
				class="scroll-item" 
				v-for="(item,index) in scrollList" 
				:key="index"
				@click="changeBar(index)"
			>
				<text :class="scrollIndex===index?'f-active-color f-active-border-color':''">{{item.name}}</text>
			</view>
		</scroll-view>
		<swiper :current="scrollIndex" @change="swiperChange" :style="{height:clientHeight}">
			<swiper-item
				v-for="(item,index) in scrollList"
				:key="index"
			>
				<view class="home-data">
					<!-- <IndexSwiper></IndexSwiper>
					<Recommend></Recommend>
					<Card carName="猜你喜欢">
						<commodityList></commodityList>
					</Card> -->
					
					<Banner></Banner>
					<Icons></Icons>
					<Card carName="热销爆品">
						<Hot></Hot>
					</Card>
					<Card carName="推荐店铺">
						<Shop></Shop>
					</Card>
				</view>
			</swiper-item>
		</swiper>
		<!-- 推荐模板 -->
		
		<!-- 运动户外、美妆。。模板 -->
		
	</view>
</template>

<script>
	import config from '../../config.js'
	import Header from '@/components/common/Header.vue'
	import Shop from '@/components/index/Shop.vue'
	import Hot from '@/components/index/Hot.vue'
	import Icons from '@/components/index/Icons.vue'
	import Banner from '@/components/index/Banner.vue'
	import commodityList from '@/components/common/commodityList.vue'
	import Card from '@/components/common/Card.vue'
	import Recommend from '@/components/index/Recommend.vue'
	import IndexSwiper from '@/components/index/IndexSwiper.vue'
	export default {
		data() {
			return {
				clientHeight:0,
				scrollIntoIndex:"top0",
				scrollIndex:0,
				scrollList:[
					{name:"推荐"},
					{name:"运动户外"},
					{name:"服饰内衣"},
					{name:"鞋靴箱包"},
					{name:"美妆个护"},
					{name:"家具数码"},
					{name:"食品婴儿"},
				]
			}
		},
		components:{
			Header,
			IndexSwiper,
			Recommend,
			Card,
			commodityList,
			Banner,
			Icons,
			Hot,
			Shop
		},
		onLoad() {
			uni.request({
				url:config.requestName+"/api/index_list/data",
				dataType:'get',
				success: (res) => {
					console.log(res)
				}
			})
		},
		onReady() {
			let view = uni.createSelectorQuery().select(".home-data");
			view.boundingClientRect(data => {
				this.clientHeight = Number(data.height) + 'px';
			}).exec();
		},
		methods: {
			changeBar(index){
				if(this.scrollIndex===index){
					return
				}
				this.scrollIndex = index;
			},
			swiperChange(e){
				this.scrollIndex = e.detail.current;
				this.scrollIntoIndex = 'top' + e.detail.current;
			}
		}
	}
</script>

<style scoped>
.scroll-content{
	width: 100%;
	height: 80rpx;
	white-space: nowrap;
}
.scroll-item{
	display: inline-block;
	padding: 10rpx 30rpx;
}
.f-active-color{
	padding-bottom: 10rpx;
	border-bottom: 6rpx solid;
}
</style>
