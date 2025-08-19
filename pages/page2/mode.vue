<template>
  <div class="flex-col page">
    <div class="flex-col group">
      <div class="flex-col justify-start items-center self-stretch text-wrapper">
        <span class="text">请选择模式</span>
      </div>
      <div class="flex-col justify-start items-center self-center relative text-wrapper_2 view " @click="goToPartyMode">
        <span class="font text_2">聚会模式</span>
      </div>
    </div>
    <div class="flex-col mt-41">
      <div class="flex-col justify-start items-center self-center text-wrapper_2" @click="goToPartyMode">
        <span class="font">情侣模式</span>
      </div>
      <div class="mt-10 flex-col justify-start items-center self-stretch section" @click="goToPartyMode">
        <div class="flex-col justify-start items-center text-wrapper_2"><span class="font">破冰模式</span></div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    components: {},
    props: {},
    data() {
      return {};
    },

    methods: {
      goToPartyMode() {
        uni.navigateTo({
          url: '/pages/lottery_wheel1' // 聚会模式页面路径
        })
      },
      goToCoupleMode() {
        uni.navigateTo({
          url: '/pages/lottery_wheel2' // 情侣模式页面路径
        })
      },
      goToIceBreakMode() {
        uni.navigateTo({
          url: '/pages/lottery_wheel3' // 破冰模式页面路径
        })
      }
    }
  };
</script>

<style scoped lang="css">
  .mt-41 {
    margin-top: 2.56rem;
  }
  .page {
    background-color: #ffffff;
    width: 100%;
    overflow-y: auto;
    overflow-x: hidden;
    height: 100%;
  }
  .group {
    height: 20.56rem;
  }
  .text-wrapper {
    padding: 9.13rem 0 8.75rem;
    background-image: url('~@/static/boarder_up.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
  .text {
    color: #000000;
    font-size: 3rem;
    font-family: 华文隶书;
    line-height: 2.31rem;
  }
  .text-wrapper_2 {
    padding: 1.75rem 0;
    background-color: #ffcbdd;
    border-radius: 0.94rem;
    width: 12.44rem;
  }
  .view {
    margin-top: -4.5rem;
  }
  .font {
    font-size: 1.5rem;
    font-family: SourceHanSansCN;
    line-height: 1.38rem;
    color: #000000;
  }
  .text_2 {
    line-height: 1.4rem;
  }
  .section {
    padding: 2rem 0 17.63rem;
    background-image: url('~@/static/boarder_down.png');
    background-size: 100% 100%;
    background-repeat: no-repeat;
  }
</style>