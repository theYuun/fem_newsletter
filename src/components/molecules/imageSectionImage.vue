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
    <img class="signupImage" :src="props.path" :alt="props.altText" :aria-label="`${props.altText}.`" />
</template>

<style scoped>
    .signupImage {
        grid-area: "image";
        width: calc(100% - 32px);
        width: 100%;
        margin: 0;
        padding: 0;
    }
</style>
