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

<style>
    .successImage {
        width: 64px;
    }
    @media (min-width: 376px) {
        .successImage {
            margin-left: 64px;
            margin-top: 48px;
        }
    }
</style>
