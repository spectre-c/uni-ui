<template>
  <view class="uni-page-head">
    <view class="uni-page-head-title">{{ title }}</view>
  </view>
</template>
<script>
export default {
  name: 'PageHead',
  props: {
    title: {
      type: String,
      default: ''
    }
  }
}
</script>
<style>
.uni-page-head {
	padding: 35upx;
	text-align: center;
	background: #f8f8f8;
}

.uni-page-head-title {
	display: inline-block;
	padding: 0 40upx;
	font-size: 30upx;
	height: 88upx;
	line-height: 88upx;
	color: #bebebe;
	box-sizing: border-box;
	border-bottom: 2upx solid #d8d8d8;
}
</style>
