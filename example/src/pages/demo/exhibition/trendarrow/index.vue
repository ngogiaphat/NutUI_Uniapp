<script lang="ts">
import { defineComponent } from 'vue'

export default defineComponent({
  props: {},
  setup() {
    return { }
  },
})
</script>

<template>
  <div class="trendarrow-demo demo">
    <h2 class="title">
      基础用法
    </h2>
    <nut-cell>
      <nut-trend-arrow :sync-text-color="false" :rate="1" />
      <nut-trend-arrow :sync-text-color="false" :rate="-0.2535" />
    </nut-cell>
    <view class="title">
      改变文字颜色
    </view>
    <nut-cell>
      <nut-trend-arrow :rate="10.2365" />
      <nut-trend-arrow :rate="-0.2535" />
    </nut-cell>
    <view class="title">
      指定小数位
    </view>
    <nut-cell>
      <nut-trend-arrow :digits="3" :rate="10.2365" />
      <nut-trend-arrow :digits="1" :rate="-0.2535" />
    </nut-cell>
    <view class="title">
      箭头在前面
    </view>
    <nut-cell>
      <nut-trend-arrow arrow-left :rate="0.2535" />
      <nut-trend-arrow arrow-left :rate="-0.2535" />
    </nut-cell>
    <view class="title">
      显示正负号
    </view>
    <nut-cell>
      <nut-trend-arrow show-sign :rate="1" />
      <nut-trend-arrow show-sign :rate="-0.2535" />
    </nut-cell>
    <view class="title">
      是否展示0
    </view>
    <nut-cell>
      <nut-trend-arrow show-sign :rate="0" />
      <nut-trend-arrow show-sign show-zero :rate="0" />
    </nut-cell>
    <view class="title">
      自定义颜色
    </view>
    <nut-cell>
      <nut-trend-arrow :rate="10.2365" rise-color="rgb(73,143,242)" />
      <nut-trend-arrow :rate="-0.2535" show-sign drop-color="rgb(255, 190, 13)" />
      <nut-trend-arrow
        :sync-text-color="false"
        show-sign
        :rate="-0.2535"
        text-color="rgb(39,197,48)"
        drop-color="rgb(255, 190, 13)"
      />
    </nut-cell>
    <view class="title">
      自定义图标
    </view>
    <nut-cell>
      <nut-trend-arrow :rate="10.2365">
        <template #up-icon>
          <nut-icon name="success" color="blue" size="18px" />
        </template>
      </nut-trend-arrow>
      <nut-trend-arrow :rate="-10.2365">
        <template #down-icon>
          <nut-icon name="failure" color="red" />
        </template>
      </nut-trend-arrow>
    </nut-cell>
  </div>
</template>

<style lang="scss">
.trendarrow-demo {
  .title {
    font-size: 14px;
    color: rgb(144, 156, 164);
    padding: 0 10px;
    font-weight: normal;
  }
  .nut-trend-arrow {
    margin-right: 10px;
  }
}
</style>

<route lang="json">
{
  "style": {
    "navigationBarTitleText": "TrendArrow"
  }
}
</route>
