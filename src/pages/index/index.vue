<template>
  <view>
    <uni-title title="布局组件" type="line"></uni-title>
    <uni-list>
      <uni-list-item v-for="(layout, index) in layouts" :key="index" :title="layout.name" @click="goDetailPage(layout)" />
    </uni-list>
    <uni-title title="基础组件" type="line"></uni-title>
    <uni-list>
      <uni-list-item v-for="(view, index) in views" :key="index" :title="view.name" @click="goDetailPage(view)" />
    </uni-list>
    <uni-title title="功能组件" type="line"></uni-title>
    <uni-list>
      <uni-list-item v-for="(func, index) in functionals" :key="index" :title="func.name" @click="goDetailPage(func)" />
    </uni-list>
    <uni-title title="导航" type="line"></uni-title>
    <uni-list>
      <uni-list-item v-for="(navi, index) in navigations" :key="index" :title="navi.name" @click="goDetailPage(navi)" />
    </uni-list>
  </view>
</template>
<script>
  import uniList from '@/components/uni-list/uni-list.vue'
  import uniListItem from '@/components/uni-list-item/uni-list-item.vue'
  import uniTitle from '@/components/uni-title/uni-title.vue'
  export default {
    components:{
      uniTitle,
      uniList,
      uniListItem
    },
    data() {
      return {
        layouts: [{
            name: 'Card 卡片',
            url: 'card'
          },
          {
            name: 'Grid 宫格',
            url: 'grid'
          },
          {
            name: 'List 列表',
            url: 'list'
          },
          {
            name: 'Title 标题栏',
            url: 'title'
          }
        ],
        views: [{
            name: 'Badge 数字角标',
            url: 'badge'
          },
          {
            name: 'Fab 悬浮按钮',
            url: 'fab'
          },
          {
            name: 'Fav 收藏按钮',
            url: 'fav'
          },
          {
            name: 'Icons 图标',
            url: 'icons'
          },
          {
            name: 'NoticeBar 通告栏',
            url: 'notice-bar'
          },
          {
            name: 'NumberBox 数字输入框',
            url: 'number-box'
          },
          {
            name: 'Tag 标签',
            url: 'tag'
          }
        ],
        functionals: [{
            name: 'Calendar 日历',
            url: 'calendar'
          },
          {
            name: 'Collapse 折叠面板',
            url: 'collapse'
          },
          {
            name: 'Drawer 抽屉',
            url: 'drawer'
          },
          {
            name: 'Pagination 分页器',
            url: 'pagination'
          },
          {
            name: 'SwiperDot 轮播图指示点',
            url: 'swiper-dot'
          },
          {
            name: 'Steps 步骤条',
            url: 'steps'
          },
          {
            name: 'SegmentedControl 分段器',
            url: 'segmented-control'
          },
          {
            name: 'CountDown 倒计时',
            url: 'count-down'
          },
          {
            name: 'Rate 评分',
            url: 'rate'
          },
          {
            name: 'Popup 弹出层',
            url: 'popup'
          },
          {
            name: 'IndexedList 索引列表',
            url: 'indexed-list'
          },
          {
            name: 'LoadMore 加载更多',
            url: 'load-more'
          },
          {
            name: 'SwipeAction 滑动操作',
            url: 'swipe-action'
          },
          {
            name: 'SearchBar 搜索栏',
            url: 'search-bar'
          }
        ],
        navigations: [{
            name: 'NavBar 导航栏',
            url: 'nav-bar'
          },
          {
            name: 'GoodsNav 商品导航',
            url: 'goods-nav'
          }
        ]
      }
    },
    methods: {
      goDetailPage(e) {
        let path = e.url
        uni.navigateTo({
          url: `/pages/${path}/${path}`
        })
        return false
      }
    }
  }
</script>

<style></style>
