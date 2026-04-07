<script setup>
import { ref, reactive,inject } from 'vue';

const items = reactive([
    {body:'test',username:'test','likes':0},
    {body:'test2',username:'test2','likes':1},
    {body:'test3',username:'test3','likes':2},
]);

const props = defineProps({
    apiUrl: {
        type: String,
        required: false
    }
});
const url = inject('url');
</script>

<template>
<ul>
    <li v-for="item in items">
        <slot name="item" v-bind="item"></slot>
    </li>
</ul>

{{url}}
</template>

<style scoped>
.slot-child {
  border: 1px solid #ccc;
  padding: 20px;
  margin: 20px;
}
</style>