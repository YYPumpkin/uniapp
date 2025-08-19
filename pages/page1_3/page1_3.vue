<template>
  <view class="flex-col page">
    <view class="flex-col section">
      <text class="self-center text">拍卖10点半</text>
      <text class="mt-54 self-stretch font text_2">
        每人一张手牌（作为底牌），中间摆放6张牌，两个人依次拍卖6张牌，价高者得，谁更接近10点半谁赢。
      </text>
    </view>
    <view class="mt-28 flex-col justify-start relative group">
      <view class="flex-col justify-start items-center text-wrapper">
        <text class="font text_3">https://v.douyin.com/RRmuhSr8KdA/</text>
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
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
  }
  .section {
    padding: 282.44rpx 61.07rpx 114.5rpx 99.24rpx;
    background-image: url('~@/static/boarder_up.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text {
    margin-right: 61.07rpx;
    color: #000000;
    font-size: 91.6rpx;
    font-family: 华文隶书;
    line-height: 67.42rpx;
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
    padding-top: 208.02rpx;
  }
  .text-wrapper {
    padding: 267.18rpx 0 446.56rpx;
    background-image: url('~@/static/boarder_down.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text_3 {
    margin-right: 49.62rpx;
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