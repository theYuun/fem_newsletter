<script setup>
const props = defineProps({
    text: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <p>{{ props.text }}</p>
</template>

<style>
</style>
