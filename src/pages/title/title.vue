<template>
  <view class="uni-wrap">
    <scroll-view class="scroll" scroll-y>
      <view class="example-info">
        uni-title 组件主要用于文章、列表详情的等标题展示
      </view>
      <uni-title class="uni-title" title="基础用法" sub-title="离开页面修改导航栏标题"></uni-title>
      <view class="example-body">
        <uni-list>
          <uni-list-item title="item" />
          <uni-list-item title="item" />
        </uni-list>
      </view>
      <uni-title title="竖线装饰" sub-title="副标题" type="line"></uni-title>
      <view class="example-body">
        <uni-list>
          <uni-list-item title="item" />
          <uni-list-item title="item" />
        </uni-list>
      </view>
      <uni-title title="圆形装饰" sub-title="副标题" type="circle"></uni-title>
      <view class="example-body">
        <uni-list>
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
          <uni-list-item title="item" />
        </uni-list>
      </view>
    </scroll-view>
  </view>
</template>

<script>
  let observer = null;
  import uniTitle from '@/components/uni-title/uni-title.vue'
  import uniList from '@/components/uni-list/uni-list.vue'
  import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
  export default {
    components:{
      uniTitle,
      uniList,
      uniListItem
    },
    data() {
      return {
        appear: false,
      }
    },
    onReady() {
      const systeminfo = uni.getSystemInfoSync()
      observer = uni.createIntersectionObserver(this);
      observer.relativeTo('.scroll', {
        top: -systeminfo.windowTop
      }).observe('.uni-title', (res) => {
        if (res.intersectionRatio > 0 && !this.appear) {
          uni.setNavigationBarTitle({
            title: 'Title 标题栏'
          })
        } else {
          uni.setNavigationBarTitle({
            title: '修改后的标题'
          })
        }
      })
    },
    onUnload() {
      if (observer) {
        observer.disconnect()
      }
    },
    methods: {

    }
  }
</script>

<style>
  .uni-wrap {
    /* #ifdef H5 */
    height: calc(100vh - 44px);
    /* #endif */
    /* #ifndef H5 */
    height: 100vh;
    /* #endif */
  }

  .scroll {
    height: 100%;
  }

  .example-body {
    padding: 0;
  }

  .seat {
    height: 500px;
    border: 1px red solid;
  }


  .scroll-view {
    height: 400upx;
    background: #fff;
    border: 1px solid #ccc;
    box-sizing: border-box;
  }

  .scroll-area {
    height: 1300upx;
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .notice {
    margin-top: 150upx;
    margin: 150upx 0 400upx 0;
  }

  .ball {
    width: 200upx;
    height: 200upx;
    background: #4cd964;
    border-radius: 50%;
  }
</style>
