<template>
  <view class="flex-col page">
    <view class="flex-col section">
      <text class="self-center text">血腥六一</text>
      <text class="self-stretch font mt-71">
        每人五张牌，抽到A拿出去，抽到六给对方，谁先出完谁赢，剩下几个骰子喝几口酒。（需要两幅牌）
      </text>
    </view>
    <view class="flex-col justify-start relative group mt-47">
      <view class="flex-col justify-start items-center text-wrapper">
        <text class="font text_2">https://v.douyin.com/1zZ_ioe5uwk/</text>
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
  .mt-71 {
    margin-top: 135.5rpx;
  }
  .mt-47 {
    margin-top: 89.69rpx;
  }
  .page {
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
  }
  .section {
    padding: 301.53rpx 80.15rpx 72.52rpx 99.24rpx;
    background-image: url('~@/static/boarder_up.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text {
    color: #000000;
    font-size: 91.6rpx;
    font-family: 华文隶书;
    line-height: 61.28rpx;
  }
  .font {
    font-size: 38.17rpx;
    font-family: 华文隶书;
    line-height: 45.8rpx;
    color: #000000;
  }
  .group {
    padding-top: 171.76rpx;
  }
  .text-wrapper {
    padding: 328.24rpx 0 347.33rpx;
    background-image: url('~@/static/boarder_down.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text_2 {
    width: 503.82rpx;
  }
  .image {
    width: 475.19rpx;
    height: 381.68rpx;
  }
  .pos {
    position: absolute;
    right: 97.33rpx;
    top: 0;
  }
</style>