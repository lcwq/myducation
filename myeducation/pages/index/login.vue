<template>
	<!-- #ifdef MP-WEIXIN -->
	<view>
		<view class='header'>
			<image src='../../static/image/logo.png'></image>
		</view>
		<view class='content'>
			<view>申请获取以下权限</view>
			<text>获得你的公开信息(昵称，头像、地区等)</text>
		</view>
		<button type="primary" open-type="getUserInfo" @getuserinfo="getuserinfo" withCredentials="true">微信登录</button>
	</view>
	<!-- #endif -->
</template>

<script>
	export default {
		data() {

		},
		onLoad() {
			this.wxLogin;
		},
		methods: {
			wxLogin: function() {
				wx.login({
					success: function(res) {
						var code = res.code;
						if (code) {
							console.log('获取用户登录凭证：' + code);

							// --------- 发送凭证 ------------------
							wx.request({
								url: 'https://api.obj8.com/v/api/getOpenid',
								data: {
									code: code
								},
								success: function(res) {
									console.log("res:::" + JSON.stringify(res))
									if (res.data.code == 0) {
										var openid = res.data.openid //返回openid
										console.log('openid为' + openid);
										uni.setStorageSync('openid', openid)
									}

								}
							})
							// ------------------------------------

						} else {
							console.log('获取用户登录态失败：' + res.errMsg);
						}
					}
				});
			},
			getuserinfo: function(res1) {
				console.log(res1);
				var nickName = res1.detail.userInfo.nickName;
				console.log("nickName:::" + res1.detail.userInfo.nickName);
				var imgUrl = res1.detail.userInfo.avatarUrl;
				console.log("avatarUrl:::" + res1.detail.userInfo.avatarUrl);
				uni.setStorageSync(
					'nickName', nickName
				)
				uni.setStorageSync(
					'imgUrl', imgUrl
				)

				/**
				 * 保存用户信息
				 */

				var openid = uni.getStorageSync('openid');
				if (openid == '') {
					this.wxLogin();
					return;
				}
				console.log("openid:::" + openid)
				uni.request({
					url: 'https://api.obj8.com/v/api/saveApp', //仅为示例，并非真实接口地址。
					method: 'POST',
					data: {
						openid: openid,
						nick: nickName,
						imgUrl: imgUrl
					},
					header: {
						'content-type': 'application/x-www-form-urlencoded' //自定义请求头信息
					},
					success: (res) => {
						console.log(res.data);
						if (res.data.code == 0) {
							uni.showToast({title:'登录成功,即将跳转...'});
							uni.reLaunch({
								url: '../myinfo/myinfo'
							}) 
						} else {
							uni.showToast({title:res.data});
						}

					}
				});
			}
		}
	}
</script>

<style>
	/**
	 * 微信授权登录
	 **/
	.header {
		margin: 90rpx 0 90rpx 50rpx;
		border-bottom: 1px solid #ccc;
		text-align: center;
		width: 650rpx;
		height: 300rpx;
		line-height: 450rpx;
	}

	.header image {
		width: 200rpx;
		height: 200rpx;
	}

	.content {
		margin-left: 50rpx;
		margin-bottom: 90rpx;
	}

	.content text {
		display: block;
		color: #9d9d9d;
		margin-top: 40rpx;
	}

	.bottom {
		border-radius: 80rpx;
		margin: 70rpx 50rpx;
		font-size: 35rpx;
	}
</style>
