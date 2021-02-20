<template>
	<view class="header">
		<!-- 头部 -->
		<view class="wx-nav" :style="{'height':globalData.menuHeight+'px','marginTop':globalData.menuTop+'px'}">
			<view class="iconfont icon-fangdajing"></view>
			<text>百年奥来</text>
			<view class="iconfont icon-xiaoxi"></view>
		</view>
	</view>
	
</template>

<script>
	export default{
		data(){
			return{
				// 数据都是根据当前机型进行计算，这样的方式兼容大部分机器
				globalData: {
					menuTop: 0, // 胶囊距顶部距离
					menuHeight: 0, // 胶囊高度（自定义内容可与胶囊高度保证一致）
				}
			}
		},
		created(){
			// 获取系统信息
			const systemInfo = uni.getSystemInfoSync();
			// 胶囊按钮位置信息
			const menuButtonInfo = uni.getMenuButtonBoundingClientRect()||"";
			this.globalData.menuTop = menuButtonInfo.top;
			this.globalData.menuHeight = menuButtonInfo.height;
			uni.setStorage({
				key: 'globalData',
				data: JSON.stringify(this.globalData),
			});
			console.log(this.globalData)
		}
	}
</script>

<style scoped>
	.wx-nav{
		width: 100%;
		display: flex;
		justify-content: space-around;
		align-items: center;
	}
</style>
