<script setup>
    defineProps(['name'])
    defineEmits(['enlargeText'])
</script>

<template>
  <h1>My name is {{ name }}</h1>
  <button @click="$emit('enlargeText')">Enlarge text</button>
  <slot />
</template>
