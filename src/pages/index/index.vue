<template>
  <Layout title="首页" :is-show-header="false">
    <view class="index-page pb-20 bg-[#f4f5f7] overflow-hidden">
      <!-- 顶部灰色背景区 - 增加弧度感 -->
      <view class="header-section pt-10 pb-20 px-6 rounded-b-[80rpx] mb-[-80rpx] relative z-0">
        <view class="flex items-center mb-6">
          <nut-avatar size="large"
            src="https://img12.360buyimg.com/imagetools/jfs/t1/143702/31/16654/116794/5fc6f541E75be8cdd/cecf272430264211.jpg" />
          <view class="ml-4">
            <view class="text-3xl font-bold text-gray-900 tracking-tight">早上好，Sarah!</view>
            <view class="text-base text-gray-500 mt-1">继续加油！</view>
          </view>
        </view>

        <!-- 目标体重进度卡片 -->
        <view class="bg-white rounded-[44rpx] p-8 shadow-sm border border-gray-50/50">
          <view class="flex justify-between items-center mb-4">
            <text class="text-base font-bold text-gray-800">目标体重进度</text>
            <view class="text-xs text-gray-500 font-medium tracking-tighter">
              <text class="font-bold text-gray-800">75.2 kg</text>
              <text class="mx-1 uppercase opacity-40">/</text>
              <text>70.0 kg</text>
            </view>
          </view>
          <view class="relative h-5 bg-[#f0f0f0] rounded-full overflow-hidden">
            <view
              class="absolute left-0 top-0 h-full bg-[#4ba34e] rounded-full flex items-center justify-end pr-5 transition-all duration-700 ease-out"
              :style="{ width: '85%' }">
              <text class="text-xs text-white font-black">85%</text>
            </view>
          </view>
        </view>
      </view>

      <!-- 今日打卡大按钮 -->
      <view class="px-6 mb-8 relative  z-10">
        <nut-button block type="primary"
          class="h-16 rounded-[32rpx] text-2xl font-bold tracking-[.2em] shadow-lg active:scale-95 transition-transform"
          style="background-color: #4ba34e; border: none;">
          今日打卡
        </nut-button>
      </view>

      <!-- 三列功能卡片 -->
      <view class="px-6 flex gap-2 relative z-10">

        <!-- 步数同步 -->
        <view
          class="feature-card flex-1 bg-white rounded-[32rpx] p-2 flex flex-col items-center shadow-sm border border-gray-50/50">
          <text class="text-[26rpx] font-bold text-gray-800 mb-0.5">步数同步</text>
          <text class="text-[22rpx] text-gray-400 font-medium mb-0.5">实时步数</text>
          <text class="text-[40rpx] font-black text-[#4ba34e] mb-0.5 tracking-tighter">5,632</text>
          <view class="relative flex items-center justify-center">
            <nut-circle-progress progress="70" stroke-width="8" radius="42" color="#4ba34e" stroke-background="#f2f2f2">
              <view class="flex flex-col items-center">
                <text class="text-[24rpx] text-gray-400 font-bold leading-none">目标</text>
                <text class="text-[24rpx] font-black text-gray-800 leading-tight">8000 步</text>
              </view>
            </nut-circle-progress>
          </view>
        </view>

        <!-- 记录体重 -->
        <view
          class="feature-card flex-1 bg-white rounded-[32rpx] p-2 flex flex-col items-center shadow-sm border border-gray-50/50">
          <text class="text-[26rpx] font-bold text-gray-800 mb-0.5">记录体重</text>
          <text class="text-[22rpx] text-gray-400 font-medium mb-1">上次记录</text>
          <view class="my-1.5  w-12 h-12 rounded-xl flex items-center justify-center border border-gray-100/50">
            <IconFont name="footprint" size="18" color="#666" />
          </view>
          <view class="flex items-baseline mb-1">
            <text class="text-[40rpx] font-black tracking-tighter">75.2</text>
            <text class="text-[22rpx] ml-1 text-gray-700 font-bold">kg</text>
          </view>
          <nut-button block shape="round" size="mini" type="info" color="#f0f0f0" text-color="#000"
            style="color: #000 !important" class="record-btn-black">
            记录
          </nut-button>
        </view>

        <!-- 查看食谱 -->
        <view
          class="feature-card flex-1 bg-white rounded-[32rpx] p-2 flex flex-col items-center shadow-sm border border-gray-50/50">
          <text class="text-[26rpx] font-bold text-gray-800 mb-2">查看食谱</text>
          <view class="w-full aspect-[4/3] rounded-[24rpx] overflow-hidden mb-2 bg-[#f8f8f8]">
            <image src="" mode="aspectFill" class="w-full h-full opacity-90" />
          </view>
          <text class="text-[24rpx] font-black text-gray-800 mb-1">查看菜单</text>
          <nut-tag color="#e9f5e9" text-color="#4ba34e" class="tag-14"
            style="font-size: 20rpx !important;">低卡早餐</nut-tag>
        </view>
      </view>

    </view>
  </Layout>
</template>

<script setup>
import Layout from "@/layout/index.vue";
import { IconFont } from "@nutui/icons-vue-taro";
</script>

<style lang="scss">
.index-page {
  background-color: #f4f5f7;
  min-height: 100vh;
}

.feature-card {
  justify-content: space-between;
}

/* 按钮样式微调 */
.nut-button--primary {
  box-shadow: 0 8rpx 20rpx rgba(75, 163, 78, 0.15);
}

/* 覆盖 NutUI 圆环样式 */
.tag-14 {
  width: 110rpx;
  height: 44rpx;
  font-size: 20rpx !important;
  justify-content: center;
  border-radius: 55rpx;
}

/* 强制穿透覆盖 NutUI 内部组件 */
:deep(.record-btn-black) {
  color: #000 !important;

  .nut-button__text {
    color: #000 !important;
  }
}

:deep(.tag-14) {
  font-size: 20rpx !important;

  .nut-tag__text {
    font-size: 20rpx !important;
  }
}
</style>
