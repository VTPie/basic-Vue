<script setup>
  import { ref } from 'vue';
  import Child from './components/Child.vue';
  
  const postFontSize = ref(1)
</script>

<template>
  <h1>This is my basic-vue project</h1>
  <div :style="{ fontSize: postFontSize + 'em' }">
    <Child name="Phong" @enlargeText="postFontSize += 0.1">
      This is content distribution with slots
    </Child>
  </div>
</template>

<style>
</style>
