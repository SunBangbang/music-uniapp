<template>
	<view class="container">
		<view class="u-demo-block__content">
		    <u-row justify="space-between" customStyle="margin-bottom: 10px">
		        <u-col span="3">
		            <view class="demo-layout bg-purple-light">
						<text class="title">编辑资料</text>
					</view>
		        </u-col>
		        <u-col span="3">
		            <view class="demo-layout bg-purple">
						<u--image src="/static/avatar.png" shape="circle" 
						 width="60px" height="60px" ></u--image>
					</view>
		        </u-col>
		    </u-row>
		</view>
		<!--表单开始-->
		<u--form labelPosition="left" :model="model1"
			:rules="rules" ref="form1">
					<u-form-item label="昵称" prop="userInfo.name"
						borderBottom ref="item1">
						<u--input v-model="model1.userInfo.name" border="none"></u--input>
					</u-form-item>
					<u-form-item label="性别" prop="userInfo.sex"
						borderBottom @click="showSex = true; hideKeyboard()" ref="item1">
									<u--input
										v-model="model1.userInfo.sex"
										disabled
										disabledColor="#ffffff"
										placeholder="请选择性别"
										border="none"
									></u--input>
									<u-icon
										slot="right"
										name="arrow-right"
									></u-icon>
					</u-form-item>
		</u--form>
		<!--表单结束-->
	</view>
</template>

<script>
	export default {
		data() {
			return {
				
			}
		},
		methods: {
			
		}
	}
</script>

<style lang="scss">
	.container{
		padding:40upx;
		background-color: #fff;
		.title{
			font-size: 40upx;
			color: #000;
			font-weight: bold;
			line-height: 60upx;
		}
	}
</style>
