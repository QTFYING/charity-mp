<script lang="ts" setup>
import NavBar from '@/components/nav-bar/nav-bar.vue';
import TabBar from '@/components/tab-bar/tab-bar.vue';

definePage({
  name: 'Goods',
  title: '好物',
  style: {
    navigationBarTitleText: '好物',
    navigationStyle: 'custom',
  },
  meta: {
    ignoreAuth: true,
  },
  tabBar: {
    index: 3,
  },
});
</script>

<template>
  <view class="">
    <NavBar left-text="" :left-arrow="false" safe-area-inset-top placeholder :fixed="true">
      好物
    </NavBar>
    <view class="p-4">
      好物
    </view>
    <TabBar :index="3" />
  </view>
</template>

<style lang="scss" scoped>
//
</style>
