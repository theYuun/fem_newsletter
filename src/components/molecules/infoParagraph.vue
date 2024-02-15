<script setup>
const props = defineProps({
    text: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <p class="infoParagraph">{{ props.text }}</p>
</template>

<style>
    .infoParagraph {
        margin-top: 20px;
        line-height: 1.5rem;
    }
</style>
