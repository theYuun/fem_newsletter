<script setup>
const props = defineProps({
    path: {
        type: String,
        required: true,
    },
    altText: {
        type: String,
    }
})
</script>

<template>
    <img :src="props.path" :alt="props.altText" :aria-label="`${props.altText}.`" />
</template>

<style scoped>
</style>
