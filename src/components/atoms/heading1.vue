<script setup>
const props = defineProps({
    text: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <h1>{{ props.text }}</h1>
</template>

<style scoped>
</style>
