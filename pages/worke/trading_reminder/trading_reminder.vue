<template>
    <view>
        <view class="uni-list-cell" hover-class="uni-list-cell-hover" v-for="(item,index) in list" :key="index">
            <view class="uni-list-cell-navigate uni-navigate-right">
                {{item}}
            </view>
        </view>

    </view>
</template>

<script>
    export default {
        data() {
            return {}
        },
        methods:{
        },
        onload:{
        },
    }
</script>

<style>

</style>
