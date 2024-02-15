<script setup>
const props = defineProps({
    data: {
        type: String,
        required: true,
    },
    index: {
        type: String,
    }
})
</script>

<template>
    <li>{{ props.data }}</li>
</template>

<style>
    li {
        padding-left: 37px;
        line-height: 1.5rem;
        position: relative;
    }
</style>
