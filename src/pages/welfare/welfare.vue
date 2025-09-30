<script lang="ts" setup>
import NavBar from '@/components/nav-bar/nav-bar.vue';
import TabBar from '@/components/tab-bar/tab-bar.vue';

definePage({
  name: 'Welfare',
  title: '公益',
  style: {
    navigationBarTitleText: '公益',
    navigationStyle: 'custom',
  },
  meta: {
    ignoreAuth: true,
  },
  tabBar: {
    index: 2,
  },
});
</script>

<template>
  <view class="">
    <NavBar left-text="" :left-arrow="false" safe-area-inset-top placeholder :fixed="true">
      公益
    </NavBar>
    <view class="p-4">
      公益
    </view>
    <TabBar :index="2" />
  </view>
</template>

<style lang="scss" scoped>
//
</style>
