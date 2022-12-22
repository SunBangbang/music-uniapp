<template>
	<view class="container">
		<view class="container1">
			<u-swiper :list="list1" @change="change" @click="click" class="s-img"></u-swiper>
			<!--音乐3张图片开始-->
			<view class="u-demo-block__content nav-title">
				<u-row justify="space-between" customStyle="margin-bottom: 10px;">
					<u-col span="3">
						<view class="demo-layout bg-purple-light">
							<text>音乐</text>
						</view>
					</u-col>
					<u-col span="2">
						<view class="demo-layout bg-purple nav-title-right">
							<text class="p1">更多</text>
							<view class="iconfont icon-gengduo"></view>
						</view>
					</u-col>
				</u-row>
				<u-scroll-list>
					<view v-for="(item, index) in navList" :key="index" class="nav">
						<view class="nav-item">
							<image :src="item.imgSrc" mode="widthFix"></image>
							<text>{{item.desc}}</text>
						</view>
					</view>
				</u-scroll-list>
			</view>
			<!--音乐3张图片结束-->
		</view>
		<view class="container2">
			<!--每日知识卡片开始-->
			<view class="u-demo-block__content nav-title kp-title">
				<u-row justify="space-between" customStyle="margin-bottom: 10px;">
					<u-col span="5">
			  	<view class="demo-layout bg-purple-light">
							<text>每日知识卡片</text>
						</view>
					</u-col>
					<u-col span="2">
						<view class="demo-layout bg-purple nav-title-right">
							<view class="iconfont icon-sanjiao3 p1"></view>
							<text>播放</text>
						</view>
					</u-col>
				</u-row>
				<view class="kp" v-for="(item,index) in kpList">
					<view class="kp-item">
						<view class="kp-item-img">
							<image :src="item.imgSrc" mode="widthFix"></image>
						</view>
						<view class="kp-item-desc">
							<text>{{item.desc}}</text>
						</view>
						<view class="iconfont icon-bofang kp-item-btn">
						</view>
					</view>
				</view>

			</view>
			<!--每日知识卡片结束-->
		</view>
	</view>
</template>
<style lang="scss">
	.container {
		background-color: #D8D8D8;
		padding-bottom: 100upx;
	}

	.container1 {
		background-color: #fff;
		padding: 30upx;
	}

	.container2 {
		background-color: #F9F9F9;
		padding: 10px 30upx 30upx 30upx;
	}

	.nav-title {
		margin-top: 30upx;

		.p1 {
			margin-right: 10upx;
		}
	}

	.nav-title-left {
		text {
			font-size: 30upx;
			line-height: 30upx;
		}
	}

	.nav-title-right {
		display: flex;
		flex-direction: row;
		font-size: 24upx;
		line-height: 30upx;
	}

	//导航
	.nav {
		display: flex;
		flex-direction: row;
	}

	.nav-item {
		margin-right: 10upx;
		text-align: center;
		image {
			width: 200upx;
			height: 200upx;
			border-radius: 20upx;
		}
	}

	//卡片
	.kp-title {
		background-color: #F9F9F9;
	}

	.kp {
		height: 120upx;
		padding: 10upx;

		.kp-item {
			display: flex;
			flex-direction: row;

			.kp-item-img {
				image {
					width: 100upx;
					height: 100upx;
					border-radius: 10upx;
				}
			}

			.kp-item-desc {
				width: 200upx;
				height: 60upx;
				padding-left: 29upx;
				line-height: 100upx;
			}

			.kp-item-btn {
				margin-left: 250upx;
				font-size: 40upx;
				line-height: 100upx;
			}

		}
	}
</style>
<script>
	export default {
		data() {
			return {
				title: '音乐',

				list1: [
					'https://cdn.uviewui.com/uview/swiper/swiper1.png',
					'https://cdn.uviewui.com/uview/swiper/swiper1.png',
				],
				//导航
				navList: [{
						imgSrc: '/static/test.png',
						desc: "专注"
					},
					{
						imgSrc: '/static/test.png',
						desc: "专注"
					},
					{
						imgSrc: '/static/test.png',
						desc: "专注"
					},
					{
						imgSrc: '/static/test.png',
						desc: "专注"
					},
					{
						imgSrc: '/static/test.png',
						desc: "专注"
					},
				],
				//每日知识卡片
				kpList: [{
					imgSrc: '/static/test.png',
					desc: "月半小夜曲"
				}, ]
			}
		},
		onLoad() {
			let nickName = uni.getStorageSync("nickName")
			if (!nickName || nickName == undefined) {
				uni.navigateTo({
					url: '/pages/login/login'
				});
			}

		},
		methods: {
			change() {

			},
			click() {

			}
		}
	}
</script>
