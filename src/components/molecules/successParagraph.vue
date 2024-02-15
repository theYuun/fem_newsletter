<script setup>
const props = defineProps({
    text: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <p class="dismissParagraph">{{ props.text }}</p>
</template>

<style scoped>
    .dismissParagraph {
        margin-top: 24px;
        line-height: 1.5rem;
    }
</style>
