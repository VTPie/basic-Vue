<script setup>
    import { onMounted, onUpdated } from 'vue'
    import { ref } from 'vue';

    let count= ref(0)

    onMounted(() => {
        console.log(`the component is now mounted.`)
    })
    onUpdated(() => {
        console.log(`the component is now updated.`)
    })
</script>

<template>
    <h1>This is Lifecycle Hook component</h1>
    <h1>{{ count }}</h1>
    <button @click="count++">Add</button>
</template>
