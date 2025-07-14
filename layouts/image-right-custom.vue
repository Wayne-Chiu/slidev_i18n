<!--
  自訂的 image-right 佈局
  內容佔 2/3，圖片佔 1/3
-->
<script setup>
import { computed } from 'vue'
import { handleBackground } from '@slidev/theme-default/layoutHelper'

const props = defineProps({
  image: {
    type: String,
  },
  class: {
    type: String,
  },
})

const style = computed(() => handleBackground(props.image))
</script>

<template>
  <div class="grid grid-cols-3 w-full h-full">
    <div class="slidev-layout default col-span-2" :class="props.class">
      <slot />
    </div>
    <div class="w-full h-full" :style="style" />
  </div>
</template>