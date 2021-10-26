<template>
<view>
			<uinput label="输入框1" v-model="test" :focus="true" labelPosition="top" placeholder="请输入输入框1"></uinput>
			<view class="font14 ml10">输入框1的结果:{{test}}</view>
			<uinput label="输入框2" v-model="test2" inputBorder="bottom" borderAnimation="center"  placeholder="请输入输入框2"></uinput>
			<view class="font14 ml10">输入框2的结果:{{test2}}</view>
			<uinput label="手机号" v-model="tel" type="tel" placeholder="请输入手机号"></uinput>
			<view class="font14 ml10">手机框的结果:{{tel}}</view>
			<uinput label="验证码" type="msgcode" :send="true" placeholder="请输入验证码"></uinput>
			<view class="font14 ml10"></view>
			
			<uinput :onlyInput="true" placeholder="邮箱输入框" type="email" ></uinput>
			
			<uinput class="mt10" :onlyInput="true" placeholder="银行卡号输入框" type="bankcard" inputBorder="bottom"></uinput>
			
			<uinput type="textarea" height="300" tlposition="none" :maxlength="-1" placeholder="输入文本框">
			</uinput>
			<button @click="aaa">aaa</button>
		</view>
</template>

<script>
	import uinput from "../../components/uinput/uinput";
	export default {
		components: {
			uinput
		},
		data(){
			return{
				test:'',
				test2:'测试数据',
				tel:''
			}
		},
		methods:{
			aa(e){
				console.log(e);
			},
			aaa(){
				this.test = 'aaa';
			}
		}
	}
</script>

<style>
	
</style>