<script setup>
import ParentComponent from './components/ParentComponent.vue';
</script>

<template>
  <div>
    <ParentComponent msg="Hoş geldiniz" :count="50"></ParentComponent>
  </div>
</template>
