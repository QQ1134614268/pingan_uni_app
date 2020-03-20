<template>
	<view style="margin: 5% 5%;">
		<view style="text-align: center;">
			{{title}}
		</view>
		<view>{{content}}</view>
		<view style="text-align: center;">{{phone}}</view>
	</view>
</template>

<script>
	export default {
		data() {
			return {
			}
		},
		props: {
			title: {
				type: String,
				default: "客服热线",
			},

			content: {
				type: String,
				default: "开户过程中遇到任何问题,可拨打客服热线.开户时间: 交易日8:45-17:45."
			},
			phone: {
				type: String,
				default: "400-8888-933"
			},
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
