# README

Vue 3.x 組合式 API 官方認證，例外的情況:

- 使用了 `<script setup>` 的組件是默認私有的：一個父組件無法訪問到一個使用了 <script setup> 的子組件中的任何東西，除非子組件在其中通過 defineExpose 宏顯式暴露
- [組件上的 ref](https://staging-cn.vuejs.org/guide/essentials/template-refs.html#ref-on-component)
