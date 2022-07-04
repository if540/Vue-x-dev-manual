<script setup lang="ts">
import { ref, computed } from 'vue'
import GroupSet from './components/GroupSet.vue'
import type { IGroupSetExpose } from './components/GroupSet_type';
let $groupSet = ref<IGroupSetExpose|null>(null)
let shoppingCar = computed(() => {
  return $groupSet
})
</script>

<template lang="pug">
div
  GroupSet(ref="$groupSet")
  //- 可響應數據
  div {{ shoppingCar?.value?.inputValue }}
</template>
