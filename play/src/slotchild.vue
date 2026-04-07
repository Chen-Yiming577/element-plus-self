<script setup>
import { ref } from 'vue';

const text = ref('子组件内容');
const counter = ref(0);
</script>

<template>
  <div class="slot-child">
    <slot :test="text" :counter="counter">
        <p>这是一个测试插槽</p>
    </slot>
  </div>
  <slot name="special" style="test">
  </slot>
</template>

<style scoped>
.slot-child {
  border: 1px solid #ccc;
  padding: 20px;
  margin: 20px;
}
</style>