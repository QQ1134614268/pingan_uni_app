<template>
    <view>
        <view
                style="display: flex;justify-content: space-around;background-color: #EB344A; color: white;">
            <view>金融</view>
            <view>原油</view>
            <view>铁矿石</view>
            <view>PTA</view>
            <view>期权</view>
        </view>
        <view style="margin-left: 10rpx;margin-top: 10%;">
            <view class="">原油期货交易账户开通条件</view>
            <view class="" style="margin: 2% 5% 10% 5%;">
                <view class="">1.开通条件</view>
                <view class="">2.开通条件</view>
                <view class="">3.开通条件</view>
                <view class="">4.开通条件</view>
            </view>
        </view>
        <view style="color: #FD7E2A;font-size: 30rpx;">金融期货开户需参与监控中心的基础测试，开户预约或详情请联系客服。</view>
        <view style="display: flex;justify-content: center;margin-top: 10%;">
            <view @tap="get_customer_service(tip)"
                  style="text-align: center;height: 60rpx; width: 30%; background-color: #EB344A ;color: white;font-size: 40rpx;">
                联系客服
            </view>
        </view>
        <view style="display:flex;justify-content:space-around;position: fixed;bottom: 0rpx;text-align: center;width: 100%;">
            <view @tap="get_normal_problem">
                常见问题
            </view>
            <view @tap="attention_public('_attention')">>
                关注平安期货
            </view>
        </view>
        <uni-popup :mask-click="false" ref="showtip">
            <view class="uni-tip">
                <atpu :content="content" :phone="phone" :title="title"></atpu>
                <view class="uni-tip-group-button">
                    <text @click="cancel('tip')" class="uni-tip-button">取消</text>
                    <text @click="makePhoneCall('tip')" class="uni-tip-button">拨打</text>
                </view>
            </view>
        </uni-popup>

        <uni-popup :mask-click="false" ref="show_attention">
            <view class="uni-tip">
                <attp></attp>
                <view class="uni-tip-group-button">
                    <text @click="cancel('_attention')" class="uni-tip-button">取消</text>
                </view>
            </view>
        </uni-popup>
    </view>
</template>
<script>
	import uniPopup from '@/components/uni-popup/uni-popup.vue'
	import atpu from "@/pages/common/customer_service.vue"
	import attp from "@/pages/common/attention_public.vue"

	// 特殊品种开户
    export default {
        components: {
            atpu,
            attp,
            uniPopup,
        },
        onBackPress() {
            this.$refs['showtip'].close()
            this.$refs['show_attention'].close()
        },
        data() {
            return {
                center: "center",
                title: "开户预约",
                content: "金融期货开户需参与监控中心的基础测试,开户预约或详情请联系客服",
                phone: "400-8888-933"
            }

        },

        methods: {
            get_customer_service(open) {
                this.$refs['show' + open].open()

            },
            attention_public(open) {
                this.$refs['show' + open].open()

            },
            cancel(type) {
                this.$refs['show' + type].close()
            },
            makePhoneCall(type) {
                this.$refs['show' + type].close()
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
            get_normal_problem() {
                uni.navigateTo({
                    url: './common_problem/common_problem',
                });
            }
        },
    }
</script>

<style>
    @import url("../../../static/uni_pop.css");
</style>
