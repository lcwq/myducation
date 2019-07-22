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
					color: "#fec6be",
					imgUrl: "/static/bg20.png",
					director: "北师大名师数学绘本课，数学思维在线培养，让孩子学会思考，现在报名可免费领取399元思维启蒙礼包。",
					title: "海豚思维   ",
					icon: "/static/icon20.png   ",
					url: "https://m.haitunsiwei.com/SwdgJicD?spread_source=335",
					price: "免费领取(价值399元)   "
				}],
			};
		}
	}
</script>

<style>

</style>
