<script setup>
const props = defineProps({
    text: {
        type: String,
        required: true,
    },
    labelFor: {
        type: String,
    }
})
</script>

<template>
    <label :for="props.labelFor" :aria-label="`${props.text}.`">
        {{ props.text }}
    </label>
</template>

<style>
    label {
        font-family: "Roboto Bold";
        font-size: 0.75rem;
    }
</style>
