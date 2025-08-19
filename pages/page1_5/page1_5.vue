<template>
  <view class="flex-col page">
    <view class="flex-col section">
      <text class="self-center text">金字塔</text>
      <text class="self-stretch font mt-69">
        每人五张手牌，将另外十张牌摆成金字塔样式，每人每会和选择一张牌翻开，如果手里有一样的就对面喝，没有一样的就自己喝，金字塔越底层喝的越少（从一口往上叠加）
      </text>
    </view>
    <view class="flex-col justify-start relative group mt-77">
      <view class="flex-col justify-start items-center text-wrapper">
        <text class="font text_2">https://v.douyin.com/H_YZr0BmqaE/</text>
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
  .mt-69 {
    margin-top: 131.68rpx;
  }
  .mt-77 {
    margin-top: 146.95rpx;
  }
  .page {
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
  }
  .section {
    padding: 297.71rpx 64.89rpx 72.52rpx 99.24rpx;
    background-image: url('~@/static/boarder_up.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text {
    color: #000000;
    font-size: 91.6rpx;
    font-family: 华文隶书;
    line-height: 67.6rpx;
  }
  .font {
    font-size: 38.17rpx;
    font-family: 华文隶书;
    line-height: 45.8rpx;
    color: #000000;
  }
  .group {
    padding-top: 114.5rpx;
  }
  .text-wrapper {
    padding: 328.24rpx 0 347.33rpx;
    background-image: url('~@/static/boarder_down.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text_2 {
    width: 534.35rpx;
  }
  .image {
    width: 475.19rpx;
    height: 381.68rpx;
  }
  .pos {
    position: absolute;
    right: 95.42rpx;
    top: 0;
  }
</style>