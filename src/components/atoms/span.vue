<script setup>
const props = defineProps({
    text: String,
})
</script>

<template>
    <span v-if="props.text">{{ props.text }}</span>
    <span v-if="!props.text"><slot></slot></span>
</template>

<style scoped>
</style>
