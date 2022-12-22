<template>
	<view class="container">
		<view class="title">
			<text>Welcome to Noemo</text>
		</view>
		
		<view class="part-between"></view>
		<u--input placeholder="nnnnn" border="surround" prefixIcon="phone"
			 prefixIconStyle="font-size: 22px;color: #000" shape="circle"></u--input>
			 
		<view class="part-between"></view>
		<u-input placeholder="请输入验证码" prefixIcon="lock" 
		    prefixIconStyle="font-size: 22px;color: #000" shape="circle">
						<template slot="suffix">
							<u-code
								ref="uCode"
								@change="codeChange"
								seconds="60"
								changeText="60秒重新获取哈哈哈"
							></u-code>
							<u-button
								@tap="getCode"
								:text="tips"
								type="success"
								size="mini"
							>获取验证码</u-button>
						</template>
		</u-input>
		
		<view class="part-between"></view>
		<view class="desc"><text>未注册的手机号验证后自动创建摄图账号</text></view><view class="sub-btn"></view>
		
		<view class="part-between"></view>
		<u-button type="primary" shape="circle" text="登录"></u-button>
		
		<view class="part-between"></view>
		<view class="login-style">
			<view class="wx">
				<view class="iconfont icon-weixin style-icon">
				</view>
				<text>微信</text>
			</view>
			<view class="qq">
				<view class="iconfont icon-qq style-icon">
				</view>
				<text>QQ</text>
			</view>
		</view>
		<!--底部用户协议开始-->
		<view class="xy">
			<text>登录即同意</text> 
			<text @tap="goXy()" class="xy-text">用户协议</text>
		</view>
		<!--底部用户协议结束-->
	</view>
</template>
<style lang="scss">
	.container{
		padding: 50upx;
		display: flex;
		flex-direction: column;
		justify-content: center;
		.title{
			margin-top: 100upx;
			text-align: center;
			text{
				font-size: 50upx;
				font-weight: bold;
				color:#000;
			}
		}
		.part-between{
			margin-top: 50upx;
		}
		.desc{
			text-align: center;
			text{
				color: #ccc;
				font-size: 24upx;
			}
		}
		.login-style{
			display: flex;
			justify-content: center;
			.wx{
				width:150upx;
				height: 80upx;
				text-align:center;
				.style-icon{
					font-size: 50upx;
					line-height: 50upx;
				}
				text{
					font-size: 24upx;
					line-height: 30upx;
				}
			}
			.qq{
				width:150upx;
				height: 80upx;
				text-align:center;
				.style-icon{
					font-size: 40upx;
					line-height: 50upx;
				}
				text{
					font-size: 24upx;
					line-height: 30upx;
				}
			}
		}
		//用户协议
		.xy{
			margin-top: 250upx;
			font-size: 24upx;
			line-height: 20upx;
			color: #ccc;
			text-align: center;
			.xy-text{
				font-size: 28upx;
				text-decoration: underline;
				margin-left: 10upx;
			}
		}
	}

</style>
<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			//跳转用户协议
			goXy(){
				uni.navigateTo({
					url:"/pages/xy/xy"
				})
			},
			codeChange(val){
				console.log(val)
			},
			getCode(){
				
			}
		}
	}
</script>


