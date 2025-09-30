<script lang="ts" setup>
import NavBar from '@/components/nav-bar/nav-bar.vue';

definePage({
  name: 'Message',
  title: '消息中心',
  style: {
    navigationBarTitleText: '消息中心',
    navigationStyle: 'custom',
  },
  meta: {
    ignoreAuth: true,
  },
});
</script>

<template>
  <view class="w-full">
    <NavBar left-text="" left-arrow>
      消息中心
    </NavBar>
    <view class="mt-4 flex flex-col gap-4 px-4">
      <text>消息列表</text>
    </view>
  </view>
</template>

<style lang="postcss" scoped>

</style>
