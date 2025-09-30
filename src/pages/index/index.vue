<script setup lang="ts">
import { useToast } from 'wot-design-uni';
import NavBar from '@/components/nav-bar/nav-bar.vue';
import TabBar from '@/components/tab-bar/tab-bar.vue';
import { formatDate } from '@/utils/utility/utils';

definePage({
  name: 'Index',
  title: '首页',
  style: {
    navigationBarTitleText: '首页',
    navigationStyle: 'custom',
  },
  meta: {
    ignoreAuth: true,
  },
  tabBar: {
    index: 0,
  },
  type: 'index',
});

const router = useRouter();
const { show: showToast } = useToast();
const hasMessage = ref(true); // 有消息时为 true

const textArray = ref([
  `张先生通过公益项目捐款12.62元 ${formatDate(new Date().getTime())}`,
  `李先生通过公益项目捐款5.60元 ${formatDate(new Date().getTime())}`,
]);

const proxy = getCurrentInstance()?.proxy;

// 扫码图标点击逻辑
function onScanClick() {
  showToast('启动扫描');
}

// 如果需要等待全局逻辑执行完毕后，则必须等待 proxy?.$appLaunchedPromise，其他生命周期也是如此
onLoad(async () => {
  // 在此处可以与全局逻辑并行执行
  await proxy?.$appLaunchedPromise;
  // app中初始化加载逻辑执行完成
});

onMounted(() => {

});
</script>

<template>
  <view class="w-full">
    <NavBar left-text="" :left-arrow="false" right-text="111" :fixed="true">
      十世守善公益平台
      <template #right>
        <wd-icon name="scan" size="18px" color="#34D19D" class="mr-3" @click="onScanClick" />

        <view class="relative inline-block">
          <wd-icon name="chat" size="20px" color="#34D19D" @click="router.push({ name: 'Message' })" />
          <view v-if="hasMessage" class="absolute right-0 top-20rpx h-8px w-8px border-2 border-white rounded-full bg-red-500" />
        </view>
      </template>
    </NavBar>

    <wd-notice-bar
      :delay="3"
      color="#34D19D"
      direction="vertical"
      background-color="#f0f9eb"
      custom-class="space"
      :text="textArray"
    />

    <view class="m-20rpx rounded-10rpx from-#22c55e to-#15b9a2 bg-gradient-to-b p-20rpx">
      <view class="user-info__first__line flex items-center justify-between gap-4">
        <view class="flex items-center gap-4">
          <view>头像</view>
          <view>
            <view>爱心用户</view>
            <view>爱心积分</view>
          </view>
        </view>
        <view>爱心大使Lv.5</view>
      </view>

      <view class="user-info__second__line">
        <view>
          <text>24</text>
          <text>捐赠次数</text>
        </view>

        <view>
          <text>￥568</text>
          <text>累计金额</text>
        </view>

        <view>
          <text>226</text>
          <text>帮助人数</text>
        </view>
      </view>
    </view>

    <view class="mt-12 flex flex-center flex-col">
      <!-- 测试模板全局方法，鼠标移入可以显示其类型 -->
      <text class="mt-4">
        {{ $formatDate(new Date().getTime()) }}
      </text>
    </view>

    <view class="flex justify-center">
      <text class="title mt-4 text-primary font-500">
        13213
      </text>
    </view>

    <view class="mt-8 flex flex-col gap-4 px-4" />

    <TabBar :index="0" />
  </view>
</template>

<!-- 关于为什么使用 postcss 而不是scss，因为 scss 使用 @apply 爆警告，如果你能做到无视警告，请使用scss -->
<style lang="postcss" scoped>

</style>
