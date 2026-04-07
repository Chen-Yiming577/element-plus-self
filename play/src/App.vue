<script setup>
import { provide, ref, watch } from 'vue'
import Child from './slotchild.vue'
import Child2 from './child.vue'
import FancyList from './fancylist.vue'
import Fancylist from './fancylist.vue';

const url = ref('https://yesno.wtf/api')

provide('url', url);
</script>

<template>
  <Child>
    <template #default="child">
    <p>{{child.test}} -- {{child.counter}}</p>
    <Child2></Child2>
    </template>

    <template #special="{style}">
      <p>这是一个具名插槽 {{style}}</p>
    </template>
  </Child>
  <FancyList>
    <template #item="{body , username, likes}">
      <p>{{ body }}</p>
      <p>by {{ username }} | {{ likes }} like{{ likes !== 0 ? 's' : '' }}</p>
    </template>
  </FancyList>
</template>