<script lang="ts" setup>
const props = withDefaults(
  defineProps<{
    index?: number;
    placeholder?: boolean;
  }>(),
  {
    index: 0,
    placeholder: true,
  },
);

const router = useRouter();

function handleChange({ value }: { value: number }) {
  if (value === props.index) { return; }
  let name = '';
  switch (value) {
      case 0: name = 'Index'; break;
      case 1: name = 'Discover'; break;
      case 2: name = 'Welfare'; break;
      case 3: name = 'Goods'; break;
      case 4: name = 'My'; break;
  }
  router.pushTab({ name });
}
</script>

<template>
  <wd-tabbar
    :model-value="index" inactive-color="#9ca3af" :placeholder="placeholder" safe-area-inset-bottom fixed
    @change="handleChange"
  >
    <wd-tabbar-item title="首页">
      <template #icon>
        <view :class="[index === 0 ? 'i-lucide-house text-primary' : 'i-lucide-house text-gray']" />
      </template>
    </wd-tabbar-item>
    <wd-tabbar-item title="发现">
      <template #icon>
        <view :class="[index === 1 ? 'i-lucide-compass text-primary' : 'i-lucide-compass text-gray']" />
      </template>
    </wd-tabbar-item>
    <wd-tabbar-item title="公益">
      <template #icon>
        <view :class="[index === 2 ? 'i-lucide-hand-heart text-primary' : 'i-lucide-hand-heart text-gray']" />
      </template>
    </wd-tabbar-item>
    <wd-tabbar-item title="好物">
      <template #icon>
        <view :class="[index === 3 ? 'i-lucide-handshake text-primary' : 'i-lucide-handshake text-gray']" />
      </template>
    </wd-tabbar-item>
    <wd-tabbar-item title="我的">
      <template #icon>
        <view :class="[index === 4 ? 'i-lucide-smile text-primary' : 'i-lucide-smile text-gray']" />
      </template>
    </wd-tabbar-item>
  </wd-tabbar>
</template>

<style lang="scss" scoped>
//
</style>
