<script setup lang="ts">
import { ref } from 'vue'
import type { Ref } from 'vue'
import type { IGroupSet } from './utile_type'

let inputValue: Ref<number> = ref(2)

function btnController(event: MouseEvent) {
  let target = <HTMLInputElement|null>event.target
  if(!target) return
  if(target?.attributes['data-name']["value"] == 'btnMinus') {
    if(inputValue.value == 0) return;
    inputValue.value--;
  }
  if(target?.attributes['data-name']["value"] == 'btnPlus') {
    inputValue.value++;
  }
}

let res: IGroupSet = { inputValue }

defineExpose(res)
</script>

<template lang="pug">
div(:class="groupSet.root")
  div(:class="groupSet.btn")
    div.mouse(:class="groupSet.plus" @click="btnController" data-name="btnPlus")
    input(type="text" :value="inputValue")
    div.mouse(:class="groupSet.minus" @click.stop="btnController" data-name="btnMinus")
  div(:class="[groupSet.word, groupSet.colorRR]") (分組序號範圍 1~999)
</template>
<style src="./GroupSet.sass" module="groupSet"></style>
