<script lang="ts" setup>
import NavBar from '@/components/nav-bar/nav-bar.vue';
import TabBar from '@/components/tab-bar/tab-bar.vue';

definePage({
  name: 'Discover',
  title: '发现',
  style: {
    navigationBarTitleText: '发现',
    navigationStyle: 'custom',
  },
  meta: {
    ignoreAuth: true,
  },
  tabBar: {
    index: 1,
  },
});
</script>

<template>
  <view class="">
    <NavBar left-text="" :left-arrow="false" safe-area-inset-top placeholder :fixed="true">
      发现
    </NavBar>
    <view class="p-4">
      发现
    </view>
    <TabBar :index="1" />
  </view>
</template>

<style lang="scss" scoped>
//
</style>
