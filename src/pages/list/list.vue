<template>
  <view>
    <view class="example-info">列表组件可以在其中使用图标、略缩图或放置任何你想放的元素，使用场景如：导航菜单、列表、设置中心排版等</view>
    <view class="example-title">基础列表</view>
    <uni-list>
      <uni-list-item :show-arrow="false" title="列表文字" />
      <uni-list-item :show-arrow="false" title="列表文字" note="列表描述信息" />
      <uni-list-item :disabled="true" :show-arrow="false" title="列表禁用状态" />
    </uni-list>
    <view class="example-title">菜单列表</view>
    <uni-list>
      <uni-list-item title="列表右侧带箭头" />
      <uni-list-item title="列表右侧自定义内容">
        <template v-slot:right>
          <text style="color: #999999;">提示</text>
        </template>
      </uni-list-item>
      <uni-list-item :show-badge="true" title="列表右侧带箭头 + 角标" badge-text="12" />
      <uni-list-item title="列表左侧带略缩图" thumb="https://img-cdn-qiniu.dcloud.net.cn/new-page/uni.png" />
      <uni-list-item :show-extra-icon="true" :extra-icon="extraIcon1" title="列表左侧带扩展图标" />
      <uni-list-item :show-extra-icon="true" :extra-icon="extraIcon1" :show-switch="true" title="列表右侧带 switch"
        @switchChange="switchChange" />
      <uni-list-item :disabled="true" :show-extra-icon="true" :extra-icon="extraIcon2" :show-switch="true"
        :switch-checked="true" title="禁用状态" @switchChange="switchChange" />
    </uni-list>

  </view>
</template>

<script>
  import uniList from '@/components/uni-list/uni-list.vue'
  import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
  export default {
    components:{
      uniList,
      uniListItem
    },
    data() {
      return {
        extraIcon1: {
          color: '#007aff',
          size: '22',
          type: 'gear-filled'
        },
        extraIcon2: {
          color: '#4cd964',
          size: '22',
          type: 'image'
        }
      }
    },
    methods: {
      switchChange(e) {
        uni.showToast({
          title: 'change:' + e.value,
          icon: 'none'
        })
      }
    }
  }
</script>

<style></style>
