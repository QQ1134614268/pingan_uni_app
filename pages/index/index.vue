<template>
    <view>
        <view class='all_module_yellow'>
            <view class="div_block">
                平安期货
            </view>
            <view class="div_block">
                平安集团旗下唯一大宗商品交易平台
            </view>
            <view class="div_block">
                客服热线: 400-8888-933
            </view>
            <view class="div_block">
                (交易日8:30-凌晨02:30)
            </view>
        </view>
        <view class='all_module_white div_blue' style="text-align:left">
            <view class="div_black " style="display: inline-block; text-align:left">
                <img src="/static/logo.png" style="height: 20%;width:100% ;margin :0cm;">
            </view>
            <view style="display: inline-block">
                三月股指原油交易月
                <br>
                新用户最高可赢850元加油卡
            </view>
            <view style="display: inline-block">
                立即参与
            </view>
        </view>

        <view class='all_module_white'>
            <view style="text-align:left">
                <view style="display: inline-block; text-align:left">
                    <img src="/static/logo.png">
                    <br/>
                    保证金计算器
                </view>
                <view style="display: inline-block; text-align:left">
                    <img src="/static/logo.png">
                    <br/>
                    适当性测试
                </view>
                <view style="display: inline-block; text-align:left">
                    <img src="/static/logo.png">
                    <br/>
                    交易提醒
                </view>
            </view>
            <view style="text-align:left">
                <view style="display: inline-block; text-align:left">
                    <img src="/static/logo.png">
                    <br/>
                    特殊品种开户
                </view>
                <view style="display: inline-block; text-align:left">
                    <img src="/static/logo.png">
                    <br/>
                    客服热线
                </view>
            </view>
        </view>
        <view style="background-color: yellow;">
            <view style="display:inline-block;">
                <img src="/static/logo.png">
                <br/>
                业务服务
            </view>
            <view style="display:inline-block;">
                <img src="/static/logo.png">
                <br/>
                交易服务
            </view>
            <view @tap="open_account" style="display:inline-block;">
                <img src="/static/logo.png">
                <br/>
                开户办理
            </view>
        </view>
    </view>

</template>

<script>
    export default {
        // import 'element-ui/lib/theme-chalk/index.css'

        name: 'home',
        data() {
            return {}

        },
        onLoad() {

        },
        methods: {
            open_account() {
                uni.navigateTo({
                    url: '../start/start',
                });
            }
        }
    }


</script>

<style>
    .content {
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .logo {
        height: 200 rpx;
        width: 200 rpx;
        margin-top: 200 rpx;
        margin-left: auto;
        margin-right: auto;
        margin-bottom: 50 rpx;
    }

    .text-area {
        display: flex;
        justify-content: center;
    }

    .title {
        font-size: 36 rpx;
        color: #8f8f94;
    }
</style>
