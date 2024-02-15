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

<style>
    .dismissParagraph {
        margin-top: 24px;
        line-height: 1.5rem;
    }
    @media (min-width: 376px) {
        .dismissParagraph {
            margin: 0 64px;
            margin-top: 24px;
        }  
    }
</style>
