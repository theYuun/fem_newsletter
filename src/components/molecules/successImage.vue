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
    <img class="successImage" :src="props.path" :alt="props.altText" :aria-label="`${props.altText}.`" />
</template>

<style scoped>
    .successImage {
        width: 64px;
    }
</style>
