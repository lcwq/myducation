<template>
	<view>
		
		<view class="contentStyle" v-for="(item,index) in jsonData" :key="index" :style="{'background-color':item.color }">
			<view class="leftstyle">
				<image class="imgUrlstyle" :src="item.imgUrl"></image>
				<view class="contentStyle-price">{{item.price}}</view>
			    <uni-rate class="starstyle" activeColor="#FFA500" value="5.0" size="18">    </uni-rate>
				<!-- <view class="starstylevalue">5.0</view> -->
				
			</view>
			<view class="rightstyle">
				<image class="rightstyle-icon" :src="item.icon"></image>
				
				<view  class="rightstyle-title">{{item.title}}</view>
				<view  class="rightstyle-des">{{item.director}}</view>
				
				<a  :href="item.url">
					<image  class="buttonstyle" src="/static/01.png"   ></image>
				</a>
		
			</view>
		
		</view>
		
	</view>
</template>

<script>
	export default {
		data() {
			return {
			//精品
		jsonData: [{
			color: "#94e8d4",
			imgUrl: "/static/bg30.png",
			director: "先一步赢在未来，在线1对1编程，现在预约免费享受价值298元体验课，我们承若三大保证让您满意！",
			title: "傲梦编程   ",
			icon: "/static/icon30.png   ",
			url: "https://all-dream.com/nviews/mobile/html/appoint.html",
			price: "免费体验(价值298元)   "
		},  {
			color: "#94e8d4",
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
			};
		}
	}
</script>

<style>

</style>
