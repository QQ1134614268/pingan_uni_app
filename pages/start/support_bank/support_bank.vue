<template>
    <view>
        <view style="margin: 5% 10%;font-size: 15px;">
            目前支持11家银行卡交易，其中四家无需您自行办理银期关联,剩余七家需通过网银或银行app进行银期。关联，可入金交易。详细操作指引可关注平安期货微服务公众号，回复银行名称查询。
        </view>
        <view style="margin:20px 0 0 0;font-weight: bold">无办理银期关联</view>
        <view>
            <view class="table" style="margin: 0 100rpx">
                <view class="tr">
                    <view class="td">建设银行</view>
                </view>
                <view class="tr">
                    <view class="td">兴业银行</view>
                </view>
                <view class="tr">
                    <view class="td">民生银行</view>
                </view>
                <view class="tr">
                    <view class="td">招商银行</view>
                </view>
            </view>
        </view>
        <view style="color: #FF0000; font-size: 10px">注：招商银行需前往银行端进行银期激活</view>
        <view style="margin:20px 0 0 0;font-weight: bold">要办理银期关联</view>
        <view>
            <view class="table" style="margin: 0 100rpx">
                <view class="tr">
                    <view class="td">平安银行</view>
                    <view class="td">中信银行</view>
                </view>
                <view class="tr">
                    <view class="td">中国银行</view>
                    <view class="td">光大银行</view>
                </view>
                <view class="tr">
                    <view class="td">农业银行</view>
                    <view class="td">交通银行</view>
                </view>
                <view class="tr">
                    <view class="td">工商银行</view>
                    <view class="td"></view>
                </view>
            </view>
        </view>
        <view>
			<span style="color: #FF0000; font-size: 10px">
				注：工商银行银期办理时间仅为交易日8:30-15:30，
			</span>
            <span style="font-size: 10px">其他银行还支持交易日20:30-凌晨02:30办理。</span>

        </view>
        <view style="display:flex;justify-content: space-around;">
            <view @tap="find_common_problem">常见问题</view>
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

    // 支持的银行
    // 客服
    export default {

        onBackPress() {
            this.$refs['showtip'].close()
        },
        components: {
            uniPopup,
            attp,
        },
        name: 'home',
        data() {
            return {}
        },
        onLoad() {

        },
        methods: {
            attention_public() {
                this.$nextTick(() => {
                    this.$refs['show' + 'tip'].open()
                })
            },
            cancel(type) {
                this.$refs['show' + type].close()
            },
            find_common_problem() {
                uni.navigateTo({
                    url: '../common_problem/common_problem',
                });
            },
        }
    }
</script>

<style>
    @import url("../../../static/uni_pop.css");

    .table {
        border-right: 0;
        border-bottom: 0;
        width: 98%;
    }

    .tr {
        width: 100%;
        display: flex;
    }

    .td {
        border: 1px solid black;
        text-align: center;
        width: 100px
    }
</style>
