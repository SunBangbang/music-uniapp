<template>
	<view class="container">
		<!--头部区域开始-->
		<view class="top">
			<view class="left">
				<text class="title">倾听Ta的事</text>
				<text class="sign">{{sign}}</text>
			</view>
			<view class="right" @tap="goBj()">
				<u-avatar :src="avatar" shape="circle" size="60"></u-avatar>
			</view>
		</view>
		<!--头部区域结束-->
		<!--导航区域开始-->
		<view class="nav">
			<view class="item">
				<view class="iconfont icon-jindu nav-icon"></view>
				<text>日记分析进度</text>
			</view>
			<view class="item">
				<view class="iconfont icon-bangzhu nav-icon"></view>
				<text>帮助反馈</text>
			</view>
			<view class="item">
				<view class="iconfont icon-shezhi nav-icon"></view>
				<text>设置中心</text>
			</view>
		</view>
		<!--导航区域结束-->
		<!--今日开始-->
		<view class="today">
			<text class="flag">今日</text>
			<view class="main">
				<view class="content">
					<view class="title">
						<view class="iconfont icon-tongjifenxi-changguitongji left"></view>
						<text>今日</text>
						<view class="iconfont icon-gengduo right"></view>
					</view>
					<view class="tj">
						<view class="item">
							<text class="type">睡眠</text>
							<text class="time">0</text>
							<text class="time2"> 分钟</text>
						</view>
						<view class="item">
							<text class="type">冥想</text>
							<text class="time">0</text>
							<text class="time2"> 分钟</text>
						</view>
						<view class="item">
							<text class="type">专注</text>
							<text class="time">0</text>
							<text class="time2"> 分钟</text>
						</view>
					</view>
				</view>
			</view>
		</view>
		<!--今日结束-->
		<!--日记开始-->
		<view class="rj">
			<text class="flag">日记分析</text>
			<view class="main"></view>
		</view>
		<!--日记结束-->
	</view>
</template>

<style lang="scss">
	.container{
		background-color: #fff;
		padding-bottom: 100upx;
	}
	.top{
		background-color: #F5F5F5;
		border-radius: 0 0 80upx 80upx;
		height:300upx;
		padding: 40upx;
		display: flex;
		.left{
			width:400upx;
			height:100upx;
			.title{
				display: block;
				font-size: 40upx;
				color: #000;
				line-height: 70upx;
			}
			.sign{
				font-size: 28upx;
				line-height: 30upx;
				color:#ccc;
			}
		}
		.right{
			margin-left: 150upx;
			width: 150upx;
			height: 150upx;
			line-height: 150upx;
		}
	}
	//导航
	.nav{
		padding: 40upx 60upx;
		display: flex;
		flex-direction: row;
		justify-content: center;
		.item{
			width: 180upx;
			height: 100upx;
			margin-right: 30upx;
			text-align: center;
			.nav-icon{
				font-size: 40upx;
				line-height: 50upx;
			}
			text{
				font-size: 24upx;
				line-height: 50upx;
			}
		}
	}
	//今日
	.today{
		padding:40upx 20upx;
		.flag{
			background-color: #000;
			padding: 10upx 25upx;
			color:#fff;
			font-size:26upx;
			line-height:30upx;
			border-radius: 20upx;
		}
		.main{
			background-color: #000;
			padding:10upx 40upx;
			margin-top: 5upx;
			.content{
				background-color: #2c2c2c;
				border-radius: 20upx;
				padding:20upx;
				color:#fff;
				.title{
					height: 40upx;
					padding:5upx;
					font-size: 30upx;
					line-height: 40upx;
					display:flex;
					.left{
						margin-right:10upx;
					}
					.right{
						margin-left: 400upx;
					}
				}
				.tj{
					margin-top:30upx;
					padding:20upx;
					display: flex;
					flex-direction: row;
					.item{
						width:120upx;
						height:120upx;
						line-height: 50upx;
						background-color: #3C302D;
						border-radius: 10upx;
						margin-right: 20upx;
						padding: 20upx;
						.type{
							font-size: 24upx;
							display: block;
						}
						.time{
							font-size: 30upx;
						}
						.time2{
							font-size: 20upx;
						}
					}
				}
			}
		}
	}
	//日记
	.rj{
		margin:20upx;
		.flag{
			background-color: #000;
			padding: 10upx 25upx;
			color:#fff;
			font-size:26upx;
			line-height:30upx;
			border-radius: 20upx;
		}
		.main{
			height:300upx;
			border: 1px solid #000;
			margin-top: 5upx;
		}
	}
</style>

<script>
	export default {
		data() {
			return {
				avatar:"/static/avatar.png",
				sign:"每个人都有快乐时候,你呢?",
	
			}
		},
		methods: {
			//去编辑
			goBj(){
				uni.navigateTo({
					url: '/pages/xxbj/xxbj'
				});
			}
		}
	}
</script>
