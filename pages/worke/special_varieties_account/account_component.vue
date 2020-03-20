<template>
    <view>
        <view style="display:flex;justify-content:space-around;position: fixed;bottom: 0rpx;text-align: center;width: 100%;">
            <view @tap="get_normal_problem">
                常见问题
            </view>
            <view @tap="attention_public('_attention')">>
                关注平安期货
            </view>
        </view>
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
    import attp from "@/pages/common/attention_public.vue"

    // 特殊品种开户
    export default {
        components: {
            attp,
            uniPopup,
        },
        onBackPress() {
            this.$refs['showtip'].close()
            this.$refs['show_attention'].close()
        },
        data() {
            return {}
        },
        methods: {
            attention_public(open) {
                this.$refs['show' + open].open()

            },
            cancel(type) {
                this.$refs['show' + type].close()
            },
            get_normal_problem() {
                uni.navigateTo({
                    url: '../../start/common_problem/common_problem',
                });
            }
        },
    }
</script>

<style>
    @import url("../../../static/uni_pop.css");
</style>
