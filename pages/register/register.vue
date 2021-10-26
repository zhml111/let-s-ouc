
<template>
	<view class="content">
		<view class="input-group">
			<view class="input-row border">
				<view class="content-tab">
					<text class="title">账</text>
					<text class="title">号</text>
				</view>
				<input type="text" v-model="account" placeholder="请输入账号">
			</view>
			<view class="input-row border">
				<view class="content-tab">
					<text class="title">密</text>
					<text class="title">码</text>
				</view>
				<input type="text" password="true" v-model="pwd" placeholder="请输入密码">
			</view>
			<view class="input-row">
				<text class="title">确认密码</text>
				<input type="text" password="true" v-model="repwd" placeholder="请输入确认密码">
			</view>
		</view>
		<view class="btn-row">
			<button type="primary" class="primary" @tap="bindRegister">注册</button>
		</view>		     
	</view>
</template>

<script>
	export default {
		data() {
			return {
				account: '',
				pwd: '',
				repwd: ''
			};
		},
		methods:{
			bindRegister(){
				uni.showToast({
					icon:"none",
					title:"注册成功"
				}); 
				uni.navigateBack({//返回到首页
                    delta: 1
                });
			}
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex: 1;
		flex-direction: column;
		/* background-color: #efeff4; */
		padding: 20px;
	}
	
	.input-group {
		background-color: #ffffff;
		margin-top: 40upx;
		position: relative;
	}
	
	.input-row.border::after {
		position: absolute;
		right: 0;
		bottom: 0;
		left: 0px;
		height: 1px;
		content: '';
		-webkit-transform: scaleY(.5);
		transform: scaleY(.5);
		background-color: #c8c7cc;
	}
	
	.input-group::after {
		position: absolute;
		right: 0;
		bottom: 0;
		left: 0;
		height: 1px;
		content: '';
		-webkit-transform: scaleY(.5);
		transform: scaleY(.5);
		background-color: #c8c7cc;
	}
	
	.input-row {
		display: flex;
		flex-direction: row;
		position: relative;
	}
	
	.input-row .title,.input-row input{
		height: 70upx;
		padding: 20upx 0;
		line-height: 70upx;
	}	
	
	.action-row {
		display: flex;
		flex-direction: row;
		justify-content: center;
	}
	
	.action-row navigator {
		color: #09BB07;
		padding: 0 20px;
	}
	
	.btn-row {
		margin: 50px 0;	
	}
	
	button.primary {
		background-color: #09BB07;
	}
	
	.content-tab{
		display: flex;
		width: 4em;
		justify-content:space-between;
	}
	.input-row input{
		margin-left: 15upx;
	}
</style>