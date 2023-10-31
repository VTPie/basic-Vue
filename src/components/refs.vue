<script setup>
    import { ref, onMounted } from 'vue'
    import refsChild from './refs-child.vue';

    const inputFile = ref(null)
    const child = ref(null)

    function handleClickbtn(){
        inputFile.value.click()
    }
    onMounted(() => {
        console.log(child.value.c)
    })
</script>

<template>
    <button class="file" @click="handleClickbtn">Choose file</button>
    <input type="file" style="display: none;" ref="inputFile"/>
    <refsChild ref="child"></refsChild>
</template>

<style>
    .file{
        padding: 10px;
        border-radius: 5px;
        font-size: 1rem;
    }
</style>