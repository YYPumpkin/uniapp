<template>
  <view class="flex-col page">
    <view class="flex-col section">
      <text class="self-center text">翻牌</text>
      <text class="self-stretch font mt-47">
        两个玩家每人身前四摞牌，每摞六张，游戏开始时先翻开每摞最上面的一张，牌小的先出，按斗地主大小规则出牌。出完上一张牌可以翻下一张，注意两张一样的是对子，三张一样是炸弹，三张连着为顺子，先打完四摞者胜。败家剩几摞喝几口。
      </text>
    </view>
    <view class="flex-col justify-start relative group mt-113">
      <view class="flex-col justify-start items-center text-wrapper">
        <text class="font text_2">https://v.douyin.com/wN_9yNMlQt4/</text>
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
  .mt-47 {
    margin-top: 89.69rpx;
  }
  .mt-113 {
    margin-top: 215.65rpx;
  }
  .page {
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
  }
  .section {
    padding: 301.53rpx 61.07rpx 114.5rpx 99.24rpx;
    background-image: url('~@/static/boarder_up.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text {
    color: #000000;
    font-size: 91.6rpx;
    font-family: 华文隶书;
    line-height: 61.93rpx;
  }
  .font {
    font-size: 38.17rpx;
    font-family: 华文隶书;
    line-height: 45.8rpx;
    color: #000000;
  }
  .group {
    padding-top: 45.8rpx;
  }
  .text-wrapper {
    padding: 377.86rpx 0 324.43rpx;
    background-image: url('~@/static/boarder_down.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text_2 {
    margin-right: 64.89rpx;
    word-break: break-all;
    width: 538.17rpx;
  }
  .image {
    width: 475.19rpx;
    height: 381.68rpx;
  }
  .pos {
    position: absolute;
    right: 50%;
    transform: translateX(50%);
    top: -150rpx; /* 根据需要调整这个值 */
  }
</style>