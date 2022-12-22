<template>
	<view class="container">
		<!--顶部滑动菜单开始-->
		<u-tabs :list="list1" @click="click"></u-tabs>
		<!--顶部滑动菜单结束-->
		<!--内容开始-->
		<view v-for="(item,index) in list2" class="content">
			<view class="top">
				<view class="u-demo-block__content">
					<u-row justify="space-between" customStyle="margin-bottom: 10px">
					    <u-col span="6">
					        <view class="demo-layout bg-purple-light title">
								<text>{{item.title}}</text>
							</view>
					    </u-col>
					    <u-col span="1">
					        <view class="demo-layout bg-purple">
								<view class="rm">
									<text>热门</text>
								</view>
							</view>
					    </u-col>
					</u-row>
					<u-row justify="space-between" customStyle="margin-bottom: 10px">
					    <u-col span="6">
					        <view class="demo-layout bg-purple-light desc">
								<text>{{item.desc}}</text>
							</view>
					    </u-col>
					    <u-col span="1">
					        <view class="demo-layout bg-purple point">
								<view class="iconfont icon-xiazai point-icon"></view>
								<text>{{item.point}}</text>
							</view>
					    </u-col>
					</u-row>
				</view>
			</view>
			<view class="main">
				<u-scroll-list :indicator="false">
				    <view v-for="(item2, index2) in item.imgList" :key="index">
				        <image :src="item2.imgSrc" mode="widthFix"></image>
				    </view>
				</u-scroll-list>
			</view>
		</view>
		<!--内容结束-->
	</view>
	
</template>

<style lang="scss">
	.container{
		padding: 0 20upx;
		background-color: #fff;
	}
	.content{
		margin-top: 50upx;
	}
	.top{
		padding: 20upx;
		.title{
			font-size: 30upx;
			font-weight: bold;
			line-height: 30upx;
		}
		.rm{
			padding-left: 5upx;
			padding-right: 5upx;
			text-align: center;
			background-color: red;
			border-radius: 10upx;
			text{
				font-size: 20upx;
				line-height: 30upx;
				color: #fff;
			}
		}
		.desc{
			font-size: 24upx;
			line-height: 30upx;
			color: #ccc;
		}
		.point{
			display:flex;
			.point-icon{
				margin-right: 10upx;
				font-size: 20upx;
				line-height: 30upx;
			}
			text{
				font-size: 20upx;
				line-height: 30upx;
			}
		}
	}
	.main{
		image{
			width: 350upx;
			border-radius: 10upx;
			margin-right:20upx;
		}
	}
</style>
<script>
	export default {
		data() {
			return {
				list1: [
					{name: '情绪精灵'},
					{name: '冥想指导'},
					{name: '交流社区'},
					{name: '情绪日记'},
					{name: '心理咨询'}
				],
				//内容
				list2:[
					{title:"月亮与六便士",desc:"贫穷的纠缠,病魔的折磨",point:1204,
					 imgList:[
						 {imgSrc:"/static/test.png"},
						 {imgSrc:"/static/test.png"},
					 ],
					},
				],
			}
		},
		methods: {
			
		}
	}
</script>
