<template>
	<view style="">
		<view class='background-color-y' style="text-align:center;color: white ">
			<view class="title">
				平安期货
			</view>
			<view style="text-align:center;color: white ">
				平安集团旗下唯一大宗商品交易平台
			</view>
			<view style="text-align:center">
				客服热线: 400-8888-933
			</view>
			<view style="text-align:center">
				(交易日8:30-凌晨02:30)
			</view>
		</view>
		<view style="text-align:left;display: flex;justify-content:space-between;">
			<view style="display: flex">
				<view>
					<img src="/static/canyu.png" style="width: 80rpx; height: 80rpx">
				</view>
				<view>
					<view style="font-weight: bold;font-size:15px;">
						三月<span style="color: #FF9900">股指原油</span>交易月
					</view>
					<view style="font-size:12px;color:#A4A4A4;">
						新用户最高可赢<span style="color: #FF9900">850元</span>加油卡
					</view>
				</view>
			</view>
			<view style="margin-top: 10rpx;background-color: #FF6600;font-weight: bold;font-size: 15px;width: 250rpx;height: 50rpx;"
			 @tap="open_account">
				<span style="color:#FF6600;color: white;">立即参与 </span>
			</view>
		</view>

		<view class='all_module_white' style="margin-top: 20rpx;">
			<view style="text-align:left;margin-top: 20rpx;">
				<view @tap="calculator_margin" style="display: inline-block; width: 33%;">
					<view>
						<img src="/static/jisuanqi.png" style="width: 80rpx;height: 80rpx">
					</view>
					<view>保证金计算器</view>
				</view>
				<view style="display: inline-block; width: 33%">
					<img src="/static/jisuanqi.png" style="width: 80rpx;height: 80rpx">
					<view>适当性测试</view>
				</view>
				<view @tap="reminder_trading" style="display: inline-block; width: 33%">
					<img src="/static/jisuanqi.png" style="width: 80rpx;height: 80rpx">
					<view>交易提醒</view>
				</view>
			</view>
			<view style="text-align:left;margin-top: 20rpx;">
				<view @tap="open_special_account" style="display: inline-block; width: 33%">
					<img src="/static/jisuanqi.png" style="width: 80rpx;height: 80rpx">
					<view>特殊品种开户</view>
				</view>
				<view @click="togglePopup('center', 'tip')" style="display: inline-block; width: 33%">
					<img src="/static/jisuanqi.png" style="width: 80rpx;height: 80rpx">
					<view>
						客服热线
					</view>

				</view>
			</view>
		</view>
		<view style="display:flex;justify-content: space-between;position: fixed;bottom: var(--window-bottom);width: 100%;background-color: yellow; float: bottom">
			<view>
				<img src="/static/yewu.png" style="width: 80rpx;height: 80rpx">
				<br />
				业务服务
			</view>
			<view>
				<img src="/static/yewu.png" style="width: 80rpx;height: 80rpx">
				<br />
				交易服务
			</view>
			<view @tap="open_account">
				<img src="/static/yewu.png" style="width: 80rpx;height: 80rpx">
				<br />
				开户办理
			</view>
		</view>
		<uni-popup ref="showtip" :type="center" :mask-click="false" @change="change">
			<view class="uni-tip">
				<atpu></atpu>
				<view class="uni-tip-group-button">
					<text class="uni-tip-button" @click="cancel('tip')">取消</text>
					<text class="uni-tip-button" @click="cancel('tip')">确定</text>
				</view>
			</view>
		</uni-popup>
	</view>
</template>

<script>
	import uniPopup from '@/components/uni-popup/uni-popup.vue'
	import atpu from "../common/customer_service.vue"

	export default {

		onBackPress() {
			this.$refs['showtip'].close()
		},
		components: {
			atpu,
			uniPopup,

		},
		name: 'home',
		data() {
			return {
				center: "center",
				content: '顶部弹 popup',
				type: '',
			}
		},
		onLoad() {

		},
		methods: {
			togglePopup(type, open) {
				console.log(888)
				switch (type) {
					case 'top':
						this.content = '顶部弹出 popup'
						break

					case 'bottom':
						this.content = '底部弹出 popup'
						break
					case 'center':
						this.content = '居中弹出 popup'
						break
				}
				this.type = type
				this.$nextTick(() => {
					this.$refs['show' + open].open()
				})
			},
			cancel(type) {
				this.$refs['show' + type].close()
			},
			change(e) {
				console.log('是否打开:' + e.show)
			},
			open_account() {
				console.log("open_account")
				uni.navigateTo({
					url: '../start/start',
				});
			},
			calculator_margin() {
				uni.navigateTo({
					url: '../worke/margin_calculator/margin_calculator',
				});
			},
			reminder_trading() {
				uni.navigateTo({
					url: '../worke/trading_reminder/trading_reminder',
				});
			},
			open_special_account() {
				uni.navigateTo({
					url: '../worke/special_varieties_account/special_varieties_account',
				});
			},
			get_customer_service() {
				// uni.navigateTo({
				// 	url: '../worke/margin_calculator/margin_calculator',
				// });
			},
			// 显示弹窗事件（处理传参）
			show() {
				this["showtip"] = true
			},

		}
	}
</script>

<style>
	.all_module_yellow {
		background-color: yellow;
	}

	/* 头条小程序组件内不能引入字体 */
	/* #ifdef MP-TOUTIAO */
	@font-face {
		font-family: uniicons;
		font-weight: normal;
		font-style: normal;
		src: url('~@/static/uni.ttf') format('truetype');
	}

	/* #endif */

	/* #ifndef APP-NVUE */
	page {
		display: flex;
		flex-direction: column;
		box-sizing: border-box;
		background-color: #efeff4;
		min-height: 100%;
		height: auto;
	}

	view {
		font-size: 14px;
		line-height: inherit;
	}

	.example {
		padding: 0 15px 15px;
	}

	.example-info {
		padding: 15px;
		color: #3b4144;
		background: #ffffff;
	}

	.example-body {
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: center;
		padding: 0;
		font-size: 14px;
		background-color: #ffffff;
	}

	/* #endif */
	.example {
		padding: 0 15px;
	}

	.example-info {
		/* #ifndef APP-NVUE */
		display: block;
		/* #endif */
		padding: 15px;
		color: #3b4144;
		background-color: #ffffff;
		font-size: 14px;
		line-height: 20px;
	}

	.example-info-text {
		font-size: 14px;
		line-height: 20px;
		color: #3b4144;
	}


	.example-body {
		flex-direction: column;
		padding: 15px;
		background-color: #ffffff;
	}

	.word-btn-white {
		font-size: 18px;
		color: #FFFFFF;
	}

	.word-btn {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		align-items: center;
		justify-content: center;
		border-radius: 6px;
		height: 48px;
		margin: 15px;
		background-color: #007AFF;
	}

	.word-btn--hover {
		background-color: #4ca2ff;
	}


	.example-body {
		/* #ifndef APP-NVUE */
		display: block;
		/* #endif */
		padding: 5px 15px;
	}

	.button {
		flex: 1;
		margin: 10px 0;
	}

	.popup-content {
		/* #ifndef APP-NVUE */
		display: block;
		/* #endif */
		background-color: #fff;
		padding: 15px;
		font-size: 14px;
	}

	/* 提示窗口 */
	.uni-tip {
		/* #ifndef APP-NVUE */
		display: flex;
		flex-direction: column;
		/* #endif */
		padding: 15px;
		width: 300px;
		background-color: #fff;
		border-radius: 10px;
	}

	.uni-tip-title {
		margin-bottom: 10px;
		text-align: center;
		font-weight: bold;
		font-size: 16px;
		color: #333;
	}

	.uni-tip-content {
		/* padding: 15px;
	 */
		font-size: 14px;
		color: #666;
	}

	.uni-tip-group-button {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		margin-top: 20px;
	}

	.uni-tip-button {
		flex: 1;
		text-align: center;
		font-size: 14px;
		color: #3b4144;
	}

	/* 插屏广告 */
	.uni-image {
		position: relative;
	}

	.image {
		width: 200px;
		height: 200px;
	}

	.uni-image-close {
		margin-top: 20px;
		text-align: center;
	}

	/* 底部分享 */
	.uni-share {
		/* #ifndef APP-NVUE */
		display: flex;
		flex-direction: column;
		/* #endif */
		background-color: #fff;
	}

	.uni-share-title {
		line-height: 60rpx;
		font-size: 24rpx;
		padding: 15rpx 0;
		text-align: center;
	}

	.uni-share-content {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: center;
		padding: 15px;
	}

	.uni-share-content-box {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: column;
		align-items: center;
		width: 200rpx;
	}

	.uni-share-content-image {
		/* #ifndef APP-NVUE */
		display: flex;
		/* #endif */
		flex-direction: row;
		justify-content: center;
		align-items: center;
		width: 60rpx;
		height: 60rpx;
		overflow: hidden;
		border-radius: 10rpx;
	}

	.content-image {
		width: 60rpx;
		height: 60rpx;
	}

	.uni-share-content-text {
		font-size: 26rpx;
		color: #333;
		padding-top: 5px;
		padding-bottom: 10px;
	}

	.uni-share-btn {
		height: 90rpx;
		line-height: 90rpx;
		font-size: 14px;
		border-top-color: #f5f5f5;
		border-top-width: 1px;
		border-top-style: solid;
		text-align: center;
		color: #666;
	}
</style>
