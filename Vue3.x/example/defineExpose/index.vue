<script setup lang="ts">
import GroupSet from './components/GroupSet.vue'
import { ref, computed } from 'vue'
import type { IGroupSet } from './components/utile_type';
let $groupSet = ref<IGroupSet|null>(null)
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
