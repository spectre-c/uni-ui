<template>
  <view class="page">
    <view class="example-info">数字角标通用来标记重点信息使用，如接受到新消息、有未读消息等</view>
    <view class="example-title">有底色</view>
    <view class="example-body">
      <uni-badge text="1" />
      <uni-badge text="2" type="primary" />
      <uni-badge text="34" type="success" />
      <uni-badge text="45" type="warning" />
      <uni-badge text="123" type="error" />
    </view>
    <view class="example-title">无底色</view>
    <view class="example-body">
      <uni-badge :inverted="true" text="1" />
      <uni-badge :inverted="true" text="2" type="primary" />
      <uni-badge :inverted="true" text="34" type="success" />
      <uni-badge :inverted="true" text="45" type="warning" />
      <uni-badge :inverted="true" text="123" type="error" />
    </view>
    <view class="example-title">迷你</view>
    <view class="example-body">
      <uni-badge text="1" size="small" />
      <uni-badge text="2" type="primary" size="small" />
      <uni-badge text="34" type="success" size="small" />
      <uni-badge text="45" type="warning" size="small" />
      <uni-badge text="123" type="error" size="small" />
    </view>
  </view>
</template>

<script>
  import uniBadge from '@/components/uni-badge/uni-badge.vue'
  export default {
    components:{
      uniBadge
    },
    data() {
      return {}
    }
  }
</script>

<style>
  .uni-badge {
    margin: 20upx;
  }
</style>
