<script setup>
import { ref, toRefs, unref, onMounted, onUnmounted, watchEffect } from 'vue'

import ChildOne from './ChildOne.vue';
import ChildTwo from './ChildTwo.vue';

const props = defineProps({
  msg: String,
  count: Number,
})

const { msg, count } = toRefs(props);

const newCount = ref(0)

newCount.value = count.value

</script>

<template>
  <h1>{{ msg }}</h1>
  <h1>{{ newCount }}</h1>

  <div class="card">
    <div>
      <button @click="newCount++">Change Count</button>
    </div>
    <ChildOne :count="newCount"></ChildOne>
    <ChildTwo :count="newCount"></ChildTwo>
  </div>
</template>

<style scoped>
.read-the-docs {
  color: #888;
}
</style>
