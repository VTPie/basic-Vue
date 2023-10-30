<script setup>
    import { reactive, computed } from 'vue'

    const author = reactive({
    name: 'John Doe',
    books: [
        'Vue 2 - Advanced Guide',
        'Vue 3 - Basic Guide',
        'Vue 4 - The Mystery'
    ]
    })
    const publishedBooksMessage = computed(() => {
        return author.books.length > 0 ? 'Yes' : 'No'
    })
    function calculateBooksMessage() {
        return author.books.length > 0 ? 'Yes' : 'No'
    }
</script>

<template>
    <p>Has published books:</p>

    <!-- Computed -->
    <span>{{ publishedBooksMessage }}</span>

    <!-- Method -->
    <p>{{ calculateBooksMessage() }}</p>
</template>
