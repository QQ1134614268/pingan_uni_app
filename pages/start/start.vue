<template>
    <view>
        <view style="text-align: center;font-weight: bold;">
            <span style="color: #EB344A;">开户准备材料</span>
        </view>
        <view style="display:flex;justify-content: space-around;">
            <view style="display: inline-block; width: 33%">
                <view>
                    <img src="/static/1.png" style="width: 80rpx; height: 100rpx">
                </view>
                <view>身份证原件</view>
            </view>
            <view style="display: inline-block; width: 33%">
                <view>
                    <img src="/static/2.png" style="width: 100rpx; height: 100rpx">
                </view>
                <view>银行卡</view>
            </view>
            <view style="display: inline-block; width: 33%">
                <view>
                    <img src="/static/3.png" style="width: 100rpx; height: 100rpx">
                </view>
                <view>笔和白纸</view>
            </view>
        </view>
        <view @tap="search_bank" style="text-align: center;font-size: 25px">支持的银行卡></view>
        <view style="text-align: center;color: #BBBBBB;margin: 10% 10% 5% 0;">开户时间: 交易日8:45-17:45</view>
        <view style="background-color: #EB344A; text-align: center;color: white;font-size: 30px;"><a
                href="http://www.baidu.com">下载开户APP</a></view>
        <view style="text-align: center;color: #EB344A;font-size: 10px;">交易日15点前完成开户,最快当天夜盘可参与交易</view>
        <view style="text-align: center;font-size: 20px;margin: 20% 0;">客服热线: 400-8888-933</view>
        <view style="display:flex;justify-content: space-around;">
            <view @tap="get_normal_problem">常见问题</view>
            <view>| 银期转账 |</view>
            <view @tap="attention_public">关注平安期货</view>
        </view>
        <uni-popup :mask-click="false" ref="showtip">
            <view class="uni-tip">
                <attp></attp>
                <view class="uni-tip-group-button">
                    <text @click="cancel('tip')" class="uni-tip-button">取消</text>
                </view>
            </view>
        </uni-popup>
    </view>
</template>

<script>

    import uniPopup from '@/components/uni-popup/uni-popup.vue'
    import attp from "@/pages/common/attention_public.vue"

    export default {
        data() {
            return {}
        },
        onLoad() {
            // uni.setNavigationBarTitle({
            // 	title: "在线开户"
            // });
        },
        components: {
            attp,
            uniPopup,
        },
        methods: {
            search_bank() {
                console.log("search_bank")
                uni.navigateTo({
                    url: './support_bank/support_bank',
                });
            },
            attention_public() {
                this.$nextTick(() => {
                    this.$refs['show' + 'tip'].open()
                })
            },
            cancel(type) {
                this.$refs['show' + type].close()
            },
            get_normal_problem() {
                uni.navigateTo({
                    url: './common_problem/common_problem',
                });
            }
        }
    }
</script>

<style>
    @import url("../../static/uni_pop.css");
</style>
