<template>
	<view class="content">

		<view>

		<!-- 	<swiper class="swiper " :indicator-dots="indicatorDots" :autoplay="autoplay" :interval="interval" :duration="duration"
			 indicator-color="rgba(255,255,255,1)" indicator-active-color="rgba(255,182,193,1)">
				<swiper-item v-for="(item,index) in  banner" :key="index" @click="onClickBanner" :data-current="item.url">
					
					<a class="astylr" :href="item.url">
						<image class="swiper-item" :mode="item.mode" :src="item.continue"> </image>
					</a>

				</swiper-item>

			</swiper> -->



			<!-- <scroll-view class="scroll-view_H" scroll-x="true" @scroll="scroll" scroll-left="0"> -->

			<view v-for="(item,index) in titleitems" :key="index" id="demo1" class="scroll-view-item_H uni-bg-red" @click="buttononclick"
			 :data-buttonId="index">
				<image class=" " :src="item.continue"> </image>
				<view class="">
					{{item.name}}
				</view>

			</view>
			<button  class="text" @click="getUserInfo"></button>

			<!-- </scroll-view> -->
			<view class="tit">
				精品推荐
			</view>
			<view class="contentStyle" v-for="(item,index) in jsonData" :key="index" :style="{'background-color':item.color }">
				<view class="leftstyle">
					<image class="imgUrlstyle" :src="item.imgUrl"></image>
					<view class="contentStyle-price">{{item.price}}</view>
					<uni-rate class="starstyle" activeColor="#FFA500" value="5.0" size="18"> </uni-rate>
					<!-- <view class="starstylevalue">5.0</view> -->

				</view>
				<view class="rightstyle">
					<image class="rightstyle-icon" :src="item.icon"></image>

					<view class="rightstyle-title">{{item.title}}</view>
					<view class="rightstyle-des">{{item.director}}</view>

					<a :href="item.url">
						<image class="buttonstyle" src="/static/01.png"></image>
					</a>

				</view>

			</view>




		</view>
	</view>
</template>

<script>
	import uniRate from "@/components/uni-rate/uni-rate.vue"
	import uniIcon from "@/components/uni-icon/uni-icon.vue"
	export default {
		components: {
			uniRate,
			uniIcon
		},
		data() {
			return {
				indicatorDots: true,
				autoplay: true,
				interval: 4000,
				duration: 1000,
				marginleft: 100,
				count: 0,
				title: 'Hello',
				url: '',
				banner: [{
					mode: "scaleToFill",
					continue: "../../static/banner1.png",
					url: "http://hi.joyskid.cn/reg2019.aspx?id=117",


				}, {
					mode: "scaleToFill",
					continue: "../../static/banner2.png",
					url: "http://www.landi.com/Api/FloorPage/index?from=dtwl&param=_byP0ifmx2Xb2qHEDcS2FfHtrYF3wOi8p9a0",
				}, {
					mode: "scaleToFill",
					continue: "../../static/banner3.png",
					url: "https://all-dream.com/nviews/mobile/html/appoint.html",
				}],
				titleitems: [{
						mode: "scaleToFill",
						continue: "../../static/icon1.png",
						url: "https://creditcard.cmbc.com.cn/wsv2/",
						name: "精品"

					}, {
						mode: "scaleToFill",
						continue: "../../static/icon2.png",
						url: "https://b.pingan.com.cn/creditcard/huodong/wxzxbkaqy4/index.shtml",
						name: "英语"
					}, {
						mode: "scaleToFill",
						continue: "../../static/icon3.png",
						url: "http://t.cn/EJQapEu",
						name: "编程"
					},
					{
						mode: "scaleToFill",
						continue: "../../static/icon4.png",
						url: "https://b.pingan.com.cn/creditcard/huodong/wxzxbkaqy4/index.shtml",
						name: "k12"
					},
					{
						mode: "scaleToFill",
						continue: "../../static/icon5.png",
						url: "https://b.pingan.com.cn/creditcard/huodong/wxzxbkaqy4/index.shtml",
						name: "数学"
					},
					{
						mode: "scaleToFill",
						continue: "../../static/icon6.png",
						url: "https://b.pingan.com.cn/creditcard/huodong/wxzxbkaqy4/index.shtml",
						name: "美术"
					},
				],
				//精品
				jsonData: [{
					color: "#fec6be",
					imgUrl: "/static/bg20.png",
					director: "北师大名师数学绘本课，数学思维在线培养，让孩子学会思考，现在报名可免费领取399元思维启蒙礼包。",
					title: "海豚思维   ",
					icon: "/static/icon20.png   ",
					url: "https://m.haitunsiwei.com/SwdgJicD?spread_source=335",
					price: "免费领取(价值399元)   "
				}, {
					color: "#94e8d4",
					imgUrl: "/static/bg30.png",
					director: "先一步赢在未来，在线1对1编程，现在预约免费享受价值298元体验课，我们承若三大保证让您满意！",
					title: "傲梦编程   ",
					icon: "/static/icon30.png   ",
					url: "https://all-dream.com/nviews/mobile/html/appoint.html",
					price: "免费体验(价值298元)   "
				}, {
					color: "#92b1ea",
					imgUrl: "/static/bg10.png",
					director: "免费领取中小学弱点知识测评，准确找到薄弱点快速提升，1对1线上课程体验或线下门店体验",
					title: "松鼠AI 1对1   ",
					icon: "/static/icon10.png   ",
					url: "https://songshuai1v1.mikecrm.com/iTRJEiS",
					price: "免费测评(价值12元)   "
				}, {
					color: "#94e8d4",
					imgUrl: "/static/bg40.png",
					director: "就是让孩子敢说，课堂好玩有趣，增强孩子表现力，CEO亲自挑选外教，地道外教，只招英美，同伴课堂孩子学习更有效！",
					title: "兰迪少儿英语   ",
					icon: "/static/icon40.png   ",
					url: "http://www.landi.com/Api/FloorPage/index?from=dtwl&param=_byP0ifmx2Xb2qHEDcS2FfHtrYF3wOi8p9a0",
					price: "免费测评(价值12元)   "
				}, {
					color: "#fec6be",
					imgUrl: "/static/bg31.png",
					director: "专注7-14岁少儿编程，小班精品直播课，985顶尖编程教师，美国CSTA标准教材，训练逻辑思维和创造力，限时免费领取试听礼包",
					title: "乔斯少儿编程   ",
					icon: "/static/icon31.png   ",
					url: "http://hi.joyskid.cn/reg2019.aspx?id=117",
					price: "免费体验(价值398元)   "
				}, {
					color: "#ffccff",
					imgUrl: "/static/bg32.png",
					director: "美国名校编程课，scratch启蒙课引导编程入门，全新升级趣味化课程内容，打卡寄送证书和礼品，我们承若三大保证让您满意！",
					title: "糖果编程   ",
					icon: "/static/icon32.png   ",
					url: "https://tangguobiancheng.com/tgpt-web/index.html?guestStudentId=27362&studentId=31019",
					price: "团购体验(价值498元)   "
				}],
				pagesindex:["index/index",
				            "english/english",
							"code/code",
							"k12/k12",
							"math/math",
							"art/art",
							]

			}
		},
		onLoad() {
			
// 			uni.login({
//   provider: 'weixin',
//   success: function (loginRes) {
// 	  console.log("wx=======");
//     console.log(loginRes);
// 	uni.getUserInfo({
//       provider: 'weixin',
//       success: function (infoRes) {
//         console.log(infoRes);
//       }
//     });
//   }
});

		},
		methods: {
			scroll: function(e) {
				console.log(e)
				this.old.scrollTop = e.detail.scrollTop
			},
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
			buttononclick: function(e) {
				console.log(e)
				var id = e.currentTarget.dataset.buttonid;
				console.log(id)
				console.log(this.pagesindex[id])
				uni.navigateTo({
					url: "/pages/"+this.pagesindex[id],
				
					success: res => {},
					fail: () => {},
					complete: () => {}
				});
				
// 				var urlcheck = this.pagesindex[id];;
// 				console.log(urlcheck)
// 				uni.request({
// 					url: urlcheck,
// 					method: 'GET',
// 					data: {},
// 					success: res => {},
// 					fail: () => {},
// 					complete: () => {}
// 				});

			}

		}
	}
</script>

<style>
	.swiper {
		height: 400upx;
		margin-top: -20upx;

	}

	.swiper-item {
		display: block;
		height: 350upx;
		width: 96%;
		line-height: 300upx;
		text-align: center;
		margin-top: 40upx;
		margin-left: 2%;
		margin-right: 2%;
		border-radius: 5px;
	}

	.astylr {
		z-index: 100;
	}

	.scroll-view_H {
		white-space: nowrap;
		width: 98%;
		height: 350upx;
		margin-left: 1%;
	}

	.scroll-view-item_H {

		width: 25%;
		display: block;
		float: left;

		text-align: center;
		font-size: 26upx;
		margin-top: 40upx;

	}

	.scroll-view-item_H image {
		width: 85upx;
		height: 85upx;
	}

	.tit {
		display: block;
		font-size: 32upx;
		font-weight: bold;
		align-content: center;
		color: #666666;
		margin: 20upx;
		padding: 40upx 0upx 10upx 0upx;
		clear: both;
	}

	/* 	.contentStyle{
		display: flex;
		width: 90%;
		height: 300upx;
		margin-top: 20upx;
		margin-left: 5%;
		margin-right: 5%;
	    border-radius: 8px;
		z-index: 100;
	}
	.imgUrlstyle
	{
		height: 176upx;
		width: 280upx;
		margin: 10upx;
	}
	.contentStyle-price{
		 color:#FF1493;
		 font-size: 22upx;
		 font-weight: bold;
		 margin-left: 30upx;
		 margin-top: -10upx;
	}
	.starstyle{
		margin: 15upx;
		margin-left: 30upx;
	}
	.leftstyle{
		display: block;
	}
	.rightstyle{
		display: block;
	}
	.rightstyle-icon{
		width: 52upx;
		height: 53upx;
		margin: 20upx;
		display: block;
	}
	.rightstyle-title{
		margin-left: 100upx;
		font-size: 31upx;
		font-weight:bold
	}
	.rightstyle-des{
		margin: 20upx;
		font-size: 23upx;
		height: 130upx;
		
		
	}
	.buttonstyle{
		
		width: 150upx;
		height:45upx;
		margin-left: 120upx;
	
	} */
	
	.text{
		color: #ff6699;
		height: 50px;
		width: 100px;
	}
</style>
