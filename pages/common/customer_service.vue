<template>
	<view style="margin: 5% 5%;">
		<view style="text-align: center;">
			客服热线
		</view>
		<view>开户过程中遇到任何问题,可拨打客服热线.开户时间: 交易日8:45-17:45.</view>
		<view style="text-align: center;">400-8888-933</view>
		<view style="display: flex;justify-content: space-around;">
			<view style="border: #000000 solid 1rpx;flex-grow: 1">
				取消
			</view>
			<view @tap="makeCall"  style="border: #000000 solid 1rpx;flex-grow: 1">
				拨打
			</view>
		</view>
	</view>
</template>

<script>
	export default {
	    data() {
	        return {}
	    },
	    methods: {
			makeCall() {
				uni.makePhoneCall({
					phoneNumber: '4008888933',
					success: (res) => {
						console.log('调用成功!')
					},
					fail: (res) => {
						console.log('调用失败!')
					}

				})
			},
		}
	}
</script>

<style>
</style>
