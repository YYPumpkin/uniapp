<template>
  <view class="flex-col page">
    <!-- 顶部图片部分 -->
    <view class="flex-col justify-start items-center self-stretch section">
      <text class="self-start font text" style="margin-left: 80rpx;">Crazy</text>  <!-- 向右移动 -->
      <text class="mt-26 self-end font" style="margin-right: 80rpx;">Party</text>  <!-- 向左移动 -->
    </view>
    
    <!-- 中间按钮部分 -->
    <view class="flex-col items-center mt-30">
      <view class="text-wrapper" @click="goToCardGame">
        <text class="font_2">卡牌游戏</text>
      </view>
      <view class="text-wrapper mt-40" @click="goToTruthOrDare">
        <text class="font_2">真心话大冒险</text>
      </view>
    </view>
    
    <!-- 底部图片部分（与顶部对称） -->
    <view class="mt-10 flex-col justify-start items-center self-stretch section-bottom">
      <view class="creator-container">
        <text class="text_3">创作者：南瓜圆圆</text>
        <image
          class="image ml-9"
          src="~@/static/cat.png"
		  style="transform: rotate(180deg);"
        />
      </view>
    </view>
  </view>
</template>

<script>
export default {
  methods: {
    goToCardGame() {
      uni.navigateTo({
        url: '/pages/page1/page1'
      })
    },
    goToTruthOrDare() {
      uni.navigateTo({
        url: '/pages/page2/mode'
      })
    }
  }
};
</script>

<style scoped lang="css">
.page {
  background-color: #ffffff;
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
}

/* 顶部图片样式 */
.section {
	padding: 9.13rem 0 8.75rem;
	background-image: url('~@/static/boarder_up.png');
	background-size: 100% 100%;
	background-repeat: no-repeat;
}

/* 底部图片样式（与顶部对称） */
.section-bottom {
	padding: 2rem 0 17.63rem;
	background-image: url('~@/static/boarder_down.png');
	background-size: 100% 100%;
	background-repeat: no-repeat;
}

/* 创作者信息容器 */
.creator-container {
  transform: rotate(180deg);
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  margin-top: 76.67rpx;
}

/* 文字样式 */
.font {
  font-size: 114.5rpx;
  font-family: 微软雅黑;
  font-weight: 700;
  color: #000000;
  line-height: 115.63rpx;
}

.text_3 {
  color: #000000;
  font-size: 45.8rpx;
  font-family: 华文隶书;
  line-height: 34.12rpx;
  transform: rotate(180deg);
}

/* 按钮样式 */
.text-wrapper {
  padding: 45.8rpx 0;
  background-color: #c7ceea;
  border-radius: 28.63rpx;
  width: 500rpx;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transition: all 0.2s;
}

.text-wrapper:nth-child(2) {
  background-color: #b5ead7;
}

.text-wrapper:active {
  transform: scale(0.98);
  opacity: 0.9;
}

.font_2 {
  font-size: 45.8rpx;
  font-family: 微軟正黑體;
  font-weight: 700;
  color: #ffffff;
  text-align: center;
}

/* 图片样式 */
.image {
  width: 103.05rpx;
  height: 103.05rpx;
}

/* 间距样式 */
.mt-53 {
  margin-top: 101.15rpx;
}

.mt-15 {
  margin-top: 28.63rpx;
}

.ml-9 {
  margin-left: 17.18rpx;
}
</style>