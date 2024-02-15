<script setup>
const props = defineProps({
    text: String,
})
</script>

<template>
    <span v-if="props.text">{{ props.text }}</span>
    <span v-if="!props.text"><slot></slot></span>
</template>

<style>
    span {
        font-family: "Roboto Bold";
        font-size: 0.75rem;
        text-align: right;
        color: var(--colorTomato);
    }
</style>
