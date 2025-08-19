<template>
  <view class="flex-col page">
    <view class="container">
	  <view class="flex-col section"></view>
      <view class="content">
        <view class="flex-row justify-between content-row">
          <view class="section_2" @click="navigateTo(1)">
            <text class="number">1</text>
          </view>
          <view class="section_2" @click="navigateTo(2)">
            <text class="number">2</text>
          </view>
        </view>

        <view class="flex-row justify-between content-row">
          <view class="section_2" @click="navigateTo(3)">
            <text class="number">3</text>
          </view>
          <view class="section_2" @click="navigateTo(4)">
            <text class="number">4</text>
          </view>
        </view>

        <view class="flex-row justify-between content-row">
          <view class="section_2" @click="navigateTo(5)">
            <text class="number">5</text>
          </view>
          <view class="section_2" @click="navigateTo(6)">
            <text class="number">6</text>
          </view>
        </view>
      </view>
    </view>
	<view class="bottom-border"></view>
  </view>
</template>

<script>
  export default {
    data() {
      return {
        // 定义六个页面的路径
        pageRoutes: [
          '/pages/page1_1/page1_1',    // 1号方框
          '/pages/page1_2/page1_2',     // 2号方框
          '/pages/page1_3/page1_3',     // 3号方框
          '/pages/page1_4/page1_4',    // 4号方框
          '/pages/page1_5/page1_5',    // 5号方框
          '/pages/page1_6/page1_6'  // 6号方框
        ]
      };
    },
    methods: {
      navigateTo(boxNumber) {
        // 根据方框编号跳转到对应页面
        const route = this.pageRoutes[boxNumber - 1];
        uni.navigateTo({
          url: route,
          success: () => {
            console.log(`跳转到${boxNumber}号页面成功`);
          },
          fail: (err) => {
            console.error(`跳转到${boxNumber}号页面失败:`, err);
            uni.showToast({
              title: `跳转失败: ${err.errMsg}`,
              icon: 'none'
            });
          }
        });
      }
    }
  };
</script>

<style lang="scss" scoped>
	.bottom-border {
	  position: absolute;
	  bottom: 0;
	  left: 0;
	  width: 100%;
	  height: 420px; /* 与顶部height相同 */
	  padding: 20rpx 65rpx 160rpx 60rpx; /* 与顶部padding相反顺序 */
	  background-image: url('~@/static/boarder_up.png');
	  background-size: 100% 100%;
	  background-repeat: no-repeat;
	  transform: rotate(180deg);
	  box-sizing: border-box; /* 确保padding包含在高度内 */
	}
	.section {
		padding: 160rpx 60rpx 20rpx 65rpx;
		background-image: url('~@/static/boarder_up.png');
		background-size: 100% 100%;
		background-repeat: no-repeat;
		flex-shrink: 0;
		height: 420px;
	}
  .page {
    width: 100%;
    height: 100vh;
    background-color: #fff;
    display: flex;
	position: relative;
    justify-content: center;
    align-items: center;
	overflow: hidden; 
  }

  .container {
    width: 100%;
    height: 100%;
    position: relative;
  }

  .background-top,
  .background-bottom {
    position: absolute;
    width: 100%;
    left: 0;
    z-index: 1;
    pointer-events: none;
  }

  .background-top {
    top: 0;
    height: 400rpx;
  }
  
  .background-bottom {
    bottom: 0;
    height: 600rpx;
  }

  .content {
    position: absolute;
    top: 200rpx; /* 从顶部边框下方开始 */
    bottom: 200rpx; /* 到底部边框上方结束 */
    left: 0;
    width: 100%;
    /* 移除原有的padding-top和padding-bottom */
    padding: 0 137rpx; /* 只保留左右内边距 */
    box-sizing: border-box;
    z-index: 2;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
  }
  
  .content-row {
    width: 100%;
  }

  /* 修改粉色方框样式，添加点击效果 */
  .section_2 {
    width: 190rpx;
    height: 190rpx;
    background-color: #ffcbdd;
    border-radius: 57rpx;
    display: flex;
    justify-content: center;
    align-items: center;
    cursor: pointer; /* 鼠标悬停变手指 */
    transition: all 0.2s ease;
    
    &:active {
      transform: scale(0.95);
      opacity: 0.8;
    }
  }

  .number {
    font-size: 80rpx;
    font-weight: bold;
    color: #ffffff !important;
    z-index: 99;
    line-height: 1.5;
  }
</style>