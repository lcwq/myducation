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
				jsonData: [ {
					color: "#fec6be",
					imgUrl: "/static/bg40.png",
					director: "就是让孩子敢说，课堂好玩有趣，增强孩子表现力，CEO亲自挑选外教，地道外教，只招英美，同伴课堂孩子学习更有效！",
					title: "兰迪少儿英语   ",
					icon: "/static/icon40.png   ",
					url: "http://www.landi.com/Api/FloorPage/index?from=dtwl&param=_byP0ifmx2Xb2qHEDcS2FfHtrYF3wOi8p9a0",
					price: "免费测评(价值12元)   "
				}]
				
			};
		}
	}
</script>

<style>

</style>
