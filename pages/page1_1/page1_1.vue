<template>
  <view class="flex-col page">
    <view class="flex-col section">
      <text class="self-center text">骗子酒馆</text>
      <text class="mt-58 self-stretch font text_2">
        　　拿出QKA，王是万能牌，每人5张手牌，谁输了谁喝酒。（规则同steam游戏骗子酒馆，详情可见视频）
      </text>
    </view>
    <view class="flex-col justify-start relative group">
      <view class="flex-col justify-start items-center text-wrapper">
        <text class="font text_3">https://v.douyin.com/qygvytvzU4U/</text>
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
    padding: 278.63rpx 64.89rpx 114.5rpx 99.24rpx;
    background-image: url('~@/static/boarder_up.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text {
    color: #000000;
    font-size: 91.6rpx;
    font-family: 华文隶书;
    line-height: 64.85rpx;
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
    padding-top: 261.45rpx;
  }
  .text-wrapper {
    padding: 217.56rpx 0 496.18rpx;
    background-image: url('~@/static/boarder_down.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text_3 {
    margin-right: 53.44rpx;
    line-height: 36.18rpx;
  }
  .image {
    width: 475.19rpx;
    height: 381.68rpx;
  }
  .pos {
    position: absolute;
    right: 93.51rpx;
    top: 20.99rpx;
  }
</style>