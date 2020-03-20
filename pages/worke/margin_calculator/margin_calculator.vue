<template>
    <view style="font-size: 33rpx;">
        <view style="text-align: center;font-size: 12px;">保证金比例不尽相同，更多详悄诘咨询</view>
        <view style="text-align: center;">400-8888-933</view>
        <view style="justify-content: space-between;display: flex;color: #B1B1B1; font-size: 33rpx;">
            <view>合约品种</view>
            <view>
                <input placeholder="如 坦纹钢" type="text" v-model="variety">
            </view>
        </view>
        <view style="display: flex; justify-content: space-between;">
            <view style="color: #B1B1B1; ">合约乘数</view>
            <view>
                <input placeholder="5" type="text" v-model="number">
            </view>
            <view>吨/手</view>
        </view>
        <view style="display: flex; justify-content: space-between;">
            <view style="color: #B1B1B1; ">行情价格</view>
            <view>
                <input placeholder="23400" type="text" v-model="price">
            </view>
            <view>元/吨</view>
        </view>
        <view style="justify-content: space-between;display: flex;color: #B1B1B1; font-size: 33rpx;">
            <view>保证金比例</view>
            <view>
                <input placeholder="15 %" type="text" v-model="percent">
            </view>
        </view>
        <view style="justify-content: space-around;display: flex;">
            <view @tap="reset">重置</view>
            <view @tap="calculate">计算</view>
        </view>
        <view style="justify-content: space-around;display: flex;">
            <view>所需保证金</view>
            <view>{{money}}元</view>
        </view>
        <view style="display: flex; justify-content: flex-end;color: #B1B1B1;font-size: 20rpx;">
            <view style="float: right;">数据裁止时日:201901 29</view>
        </view>
        <view style="font-size: 20rpx;">
            <span style="color: red;">温馨楞示:</span>进议轻仓损作，期货总权益至少为保证金金额的2倍。保证金比例会根搓交易所规定随时调整，以上测算数据仅供参考，实际数额以成友记录/保证金临控中心记景/算单数活为准。
        </view>
    </view>
</template>
<script>
    // <!-- 保证金计算器 -->

    export default {
        data() {
            return {
                money: "",
                number: "",
                percent: "",
                price: "",
                variety: "",
            }
        },
        methods: {
            reset() {
                this.money = "";
                this.number = "";
                this.percent = "";
                this.variety = "";
                this.price = "";
            },
            calculate() {
                console.log("calculate")
            },

        },
    }
</script>

<style>

</style>
