<script setup>
import ListIndex from './atoms';
const props = defineProps({
    data: {
        type: Array,
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

<style scoped>
</style>
