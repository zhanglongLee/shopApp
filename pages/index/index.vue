<template>
	<view class="content">
		<!-- 顶部滑动导航 -->
		<scroll-view scroll-x="true" class="scroll-content" :scroll-into-view="scrollIntoIndex">
			<view 
				:id="'top'+index"
				class="scroll-item" 
				v-for="(item,index) in topBar" 
				:key="index"
				@click="changeBar(index)"
			>
				<text :class="scrollIndex===index?'f-active-color f-active-border-color':''">{{item.name}}</text>
			</view>
		</scroll-view>
		<swiper :current="scrollIndex" @change="swiperChange" :style="{height:clientHeight}">
			<swiper-item
				v-for="(item,index) in newTopBar"
				:key="index"
			>
				<scroll-view scroll-y="true" :style="{height:clientHeight}">
					
					<block v-for="(k,i) in item.data" :key="i">
						<IndexSwiper v-if="k.type=='swiperList'" :dataList="k.data"></IndexSwiper>
						<Recommend v-if="k.type=='recommendList'" :dataList="k.data"></Recommend>
						<Card carName="猜你喜欢" v-if="k.type=='commodityList'">
							<commodityList :dataList="k.data"></commodityList>
						</Card>
					</block>
					
					
					<!-- <Banner></Banner>
					<Icons></Icons>
					<Card carName="热销爆品">
						<Hot></Hot>
					</Card>
					<Card carName="推荐店铺">
						<Shop></Shop>
					</Card> -->
				</scroll-view>
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
				topBar:[],
				newTopBar:[]
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
			this.__init();
		},
		onReady() {
			uni.getSystemInfo({
				success: (res) => {
					// 可视区高度 - 顶部滑动导航高度
					this.clientHeight = res.windowHeight - uni.upx2px(80) + 'px';
				}
			})
		},
		methods: {
			// 首页请求的数据
			__init(){
				uni.request({
					url:config.requestName+"/api/index_list/data",
					dataType:'get',
					success: (res) => {
						if(JSON.parse(res.data).code===0){
							let data = JSON.parse(res.data).data;
							this.topBar = data.topBar;
							this.newTopBar = this.initData(data);
						}
					}
				})
			},
			// 添加数据
			initData(res){
				let arr = [];
				for(var i=0;i<this.topBar.length;i++){
					let obj={
						data:[]
					}
					// 获取首次数据
					if(i===0){
						obj.data = res.data;
					}
					arr.push(obj);
				}
				return arr;
			},
			// 点击导航栏
			changeBar(index){
				if(this.scrollIndex===index){
					return
				}
				this.scrollIndex = index;
			},
			// 滑动切换
			swiperChange(e){
				this.scrollIndex = e.detail.current;
				this.scrollIntoIndex = 'top' + e.detail.current;
			}
		}
	}
</script>

<style scoped>
	.demo1{
		background: red;
	}
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
