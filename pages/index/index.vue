<template>
	<view>
		<button class="eButton" @tap="check()">开始验证</button>
		<textarea v-model="msg"></textarea>
		<button class="eButton" @tap="clearConsole()">清屏</button>
		<div class="bgp"></div>
	</view>
</template>

<script>
const SimpleIFAAModule = uni.requireNativePlugin('Esand-SimpleIfaaModule');
//阿里云市场appcode(从阿里云市场获取)
const APPCODE="替换为你的appcode";
export default {
	data() {
		return {
			msg:"logs",
		};
	},
	onLoad() {},
	methods: {
		check() {
			let _this=this;
			SimpleIFAAModule.sAuth(
				{
					//显示的标题
					reasonTitle: 'uni-Demo',
					//尝试一次以后返回的内容
					fallbackTitle: '请输入密码'
				},
				ret => {
					var retJson = JSON.parse(ret);
					if (retJson.code == '0') {
						//服务器验证(为了保护APPCODE, 此段逻辑建议放在服务器端)
						uni.request({
							url: 'http://simpleifaa.market.alicloudapi.com/ifaa/sAuth',
							method: 'POST',
							data: {
								ifaaMsg: retJson.msg
							},
							header: {
								Authorization: 'APPCODE '+APPCODE,
								'Content-Type': 'application/x-www-form-urlencoded; charset=UTF-8'
							},
							success: res => {
								console.log('网络请求成功' + JSON.stringify(res.data));
								_this.msg+="获取结果成功"+ JSON.stringify(res.data);
							}
						});
					}
				}
			);
		},
		clearConsole(){
			this.msg="";
		}
	}
};
</script>

<style>
.eButton {
	margin-top: 40px;
	display: inline-block;
	background-color: #f0ad4e;
}
textarea {
	text-align: left;
	font-size: 23px;
	color: white;
	width: calc(100% - 4px);
	border: #333333 2px solid;
}
.bgp {
	display: inline-block;
	position: fixed;
	left: 0px;
	top: 0px;
	width: 100%;
	height: 100%;
	background-color: #c8c7cc;
	z-index: -1;
}
view{
	text-align: center;
}
</style>
