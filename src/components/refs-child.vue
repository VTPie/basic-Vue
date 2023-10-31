<script setup>
    import { ref } from 'vue'

    const a = 1
    const b = ref(2)
    const c = ref(3)

    defineExpose({
        a,
        b
    })

</script>

<template>
</template>

<style>
</style>