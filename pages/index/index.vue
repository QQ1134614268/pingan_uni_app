<template>
    <view style="">
        <view style="background-color:#FF9900 ;text-align:center;color: white ">
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
            <view @tap="open_account"
                  style="margin-top: 10rpx;background-color: #FF6600;font-weight: bold;font-size: 15px;width: 250rpx;height: 50rpx;">
                <span style="color:#FF6600;color: white;">立即参与 </span>
            </view>
        </view>

        <view style="margin:20rpx 10rpx;text-align:center;">
            <view style="display: flex;">
                <view @tap="calculator_margin" style=" width: 33%;">
                    <view>
                        <img src="/static/jisuanqi.png" style="width: 80rpx;height: 80rpx">
                    </view>
                    <view>保证金计算器</view>
                </view>
                <view style="width: 33%">
                    <img src="/static/jisuanqi.png" style="width: 80rpx;height: 80rpx">
                    <view>适当性测试</view>
                </view>
                <view @tap="reminder_trading" style=" width: 33%">
                    <img src="/static/jisuanqi.png" style="width: 80rpx;height: 80rpx">
                    <view>交易提醒</view>
                </view>
            </view>
            <view style="margin-top: 20rpx;display: flex;">
                <view @tap="open_special_account" style="width: 33%">
                    <img src="/static/jisuanqi.png" style="width: 80rpx;height: 80rpx">
                    <view>特殊品种开户</view>
                </view>
                <view @click="get_customer_service('center', 'tip')" style="width: 33%">
                    <img src="/static/jisuanqi.png" style="width: 80rpx;height: 80rpx">
                    <view>
                        客服热线
                    </view>
                </view>
            </view>
        </view>
        <view style="text-align:center;display:flex;justify-content: space-between;position: fixed;bottom: 0rpx;width: 100%;background-color: yellow; float: bottom">
            <view>
                <view>
                    <img src="/static/yewu.png" style="width: 80rpx;height: 80rpx">
                </view>
                <view>
                    业务服务
                </view>
            </view>
            <view>
                <view>
                    <img src="/static/yewu.png" style="width: 80rpx;height: 80rpx">
                </view>
                <view>
                    交易服务
                </view>
            </view>
            <view>
                <view @tap="open_account">
                    <img src="/static/yewu.png" style="width: 80rpx;height: 80rpx">
                </view>
                <view>开户办理</view>
            </view>


        </view>
        <uni-popup :mask-click="false" :type="center" @change="change" ref="showtip">
            <view class="uni-tip">
                <atpu></atpu>
                <view class="uni-tip-group-button">
                    <text @click="cancel('tip')" class="uni-tip-button">取消</text>
                    <text @click="makePhoneCall('tip')" class="uni-tip-button">拨打</text>
                </view>
            </view>
        </uni-popup>
    </view>
</template>

<script>
    import uniPopup from '@/components/uni-popup/uni-popup.vue'
    import atpu from "@/pages/common/customer_service.vue"

    export default {
        onLoad() {

        },
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
        methods: {
            get_customer_service(type, open) {
                this.$refs['show' + open].open()
            },
            cancel(type) {
                this.$refs['show' + type].close()
            },
            makePhoneCall(type) {
                this.$refs['show' + type].close();
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
            change(e) {
                console.log('是否打开:' + e.show)
            },
            // 显示弹窗事件（处理传参）
            show() {
                this["showtip"] = true
            },
            open_account() {
                console.log("open_account");
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

        }
    }
</script>

<style>
    @import url("../../static/uni_pop.css");
</style>
