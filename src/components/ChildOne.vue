<script setup>
import { ref, toRefs, unref, onMounted, onUnmounted, watchEffect } from 'vue'

const props = defineProps({
  count: Number,
})

const { count } = toRefs(props);

const counter = ref(0)

watchEffect(async () => {
  counter.value = count.value
})

let intervalId
onMounted(() => {
  counter.value = count.value
  decrease()
})

onUnmounted(() => clearInterval(intervalId))

function decrease() {
  intervalId = setInterval(() => {
    counter.value -= 1
  }, 400);
}
</script>

<template>
  <div style="margin: 5px; padding: 5px;">
    {{ counter }}
  </div>
</template>
