<template>
    <view>
        <view class='all_module_yellow'>
            <view class="div_block">
                {{txt_const.txt1}}
            </view>
            <view class="div_block">
                {{txt_const.txt2}}
            </view>
            <view class="div_block">
                {{txt_const.txt3}}
            </view>
            <view class="div_block">
                {{txt_const.txt4}}
            </view>
        </view>
        <view class='all_module_white div_blue' style="text-align:left">
            <view class="div_black " style="display: inline-block; text-align:left">
                <img src="/static/logo.png" style="height: 20%;width:100% ;margin :0cm;">
            </view>
            <view style="display: inline-block">
                {{txt_const.txt5}}
                <br>
                {{txt_const.txt6}}
            </view>
            <view style="display: inline-block">
                {{txt_const.txt7}}
            </view>
        </view>

        <view class='all_module_white'>
            <view style="text-align:left">
                <view style="display: inline-block; text-align:left">
                    <img src="/static/logo.png">
                    <br/>
                    {{txt_const.txt8}}
                </view>
                <view style="display: inline-block; text-align:left">
                    <img src="/static/logo.png">
                    <br/>
                    {{txt_const.txt9}}
                </view>
                <view style="display: inline-block; text-align:left">
                    <img src="/static/logo.png">
                    <br/>
                    {{txt_const.txt10}}
                </view>
            </view>
            <view style="text-align:left">
                <view style="display: inline-block; text-align:left">
                    <img src="/static/logo.png">
                    <br/>
                    {{txt_const.txt11}}
                </view>
                <view style="display: inline-block; text-align:left">
                    <img src="/static/logo.png">
                    <br/>
                    {{txt_const.txt12}}
                </view>
            </view>
        </view>
        <view style="background-color: yellow;">
            <view style="display:inline-block;">
                <img src="/static/logo.png">
                <br/>
                {{txt_const.txt13}}
            </view>
            <view style="display:inline-block;">
                <img src="/static/logo.png">
                <br/>
                {{txt_const.txt14}}
            </view>
            <view style="display:inline-block;" @tap="open_account">
                <img src="/static/logo.png">
                <br/>
                {{txt_const.txt15}}
            </view>
        </view>
    </view>

</template>

<script>
    export default {
        // import 'element-ui/lib/theme-chalk/index.css'

        name: 'home',
        data() {
            return {
                txt_const: {
                    txt1: '平安期货',
                    txt2: '平安集团旗下唯一大宗商品交易平台',
                    txt3: '客服热线: 400-8888-933',
                    txt4: '(交易日8:30-凌晨02:30)',
                    txt5: '三月股指原油交易月',
                    txt6: '新用户最高可赢850元加油卡',
                    txt7: '立即参与',
                    txt8: '保证金计算器',
                    txt9: '适当性测试',
                    txt10: '交易提醒',
                    txt11: '特殊品种开户',
                    txt12: '客服热线',
                    txt13: '业务服务',
                    txt14: '交易服务',
                    txt15: '开户办理',
                }
            }

        },
        onLoad() {

        },
        methods: {
			open_account(){
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
