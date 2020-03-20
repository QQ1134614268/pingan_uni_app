<template>
    <view>
        <view :key="index" class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(item,index) in enentList">
            <view class="uni-list-cell-navigate uni-navigate-right">
                {{item.title}}
            </view>
        </view>
    </view>
</template>

<script>
    export default {
        data() {
            return {
                enentList: [{
                    title: "大涨"
                }, {
                    title: "大涨"
                }]
            }
        },
        methods: {},
        onload: {},
    }
</script>

<style>

</style>
