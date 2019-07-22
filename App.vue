<script>
	export default {
		onLaunch: function () {
			console.log('App Launch')
		},
		onShow: function () {
			console.log('App Show')
		},
		onHide: function () {
			console.log('App Hide')
		}
	}
</script>

<style>
	/*每个页面公共css */
	.contentStyle{
		display: flex;
		width: 90%;
		height: 300upx;
		margin-top: 20upx;
		margin-left: 5%;
		margin-right: 5%;
	    border-radius: 8px;
		z-index: 100;
		/* background-color: #ffccff; */
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
		/* display: inline-block */
		display: block;
	}
	.rightstyle-title{
		/* display: inline-block; */
		margin-top: -72upx;
		margin-left: 100upx;
		font-size: 31upx;
		font-weight:bold
	}
	.rightstyle-des{
		margin: 20upx;
		font-size: 23upx;
		height: 130upx;
		/* width: 58%; */
		
		
	}
	.buttonstyle{
		/* display: block; */
		width: 150upx;
		height:45upx;
		margin-left: 120upx;
		/* margin-bottom: 30upx; */
	}
</style>
