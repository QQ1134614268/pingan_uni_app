<template>
    <view>
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
    import customerService from "@/pages/common/customer_service.vue"

    export default {
        components: {
            uniPopup,
            customerService,
        },
        onBackPress() {
            this.$refs['showtip'].close()
        },
        methods: {
            togglePopup(type, open) {
                this.$nextTick(() => {
                    this.$refs['show' + open].open()
                })
            },
            cancel(type) {
                this.$refs['show' + type].close()
            },
        }
    }
</script>

<style>
    @import url("../../static/uni_pop.css");
</style>
