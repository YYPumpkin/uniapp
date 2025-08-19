<template>
  <view class="flex-col page">
    <view class="flex-col section">
      <text class="self-center text">德州扑克</text>
      <text class="mt-56 self-stretch font text_2">每人两张扑克，加注就往杯子里倒酒，谁输了谁喝。</text>
    </view>
    <view class="flex-col justify-start relative group">
      <view class="flex-col justify-start items-center text-wrapper">
        <text class="font text_3">https://v.douyin.com/XyvN-4ff0Ek/</text>
      </view>
      <image
        class="image pos"
        src="~@/static/poker.png"
      />
    </view>
  </view>
</template>

<script>
  export default {
    components: {},
    props: {},
    data() {
      return {};
    },

    methods: {},
  };
</script>

<style scoped lang="css">
  .page {
    background-color: #ffffff;
    height: 100%;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
  }
  .section {
    padding: 278.63rpx 80.15rpx 114.5rpx 99.24rpx;
    background-image: url('~@/static/boarder_up.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text {
    color: #000000;
    font-size: 91.6rpx;
    font-family: 华文隶书;
    line-height: 68.15rpx;
  }
  .font {
    font-size: 38.17rpx;
    font-family: 华文隶书;
    color: #000000;
  }
  .text_2 {
    line-height: 45.8rpx;
  }
  .group {
    margin-top: -20.99rpx;
    padding-top: 278.63rpx;
  }
  .text-wrapper {
    padding: 217.56rpx 0 496.18rpx;
    background-image: url('~@/static/boarder_down.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text_3 {
    margin-right: 61.07rpx;
    line-height: 36.11rpx;
  }
  .image {
    width: 475.19rpx;
    height: 381.68rpx;
  }
  .pos {
    position: absolute;
    right: 91.6rpx;
    top: 0;
  }
</style>