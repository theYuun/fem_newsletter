<script setup>
import ListIndex from './atoms';
const props = defineProps({
    data: {
        type: Array,
        required: true,
    }
})
</script>

<template>
    <ul>
        <ListIndex v-for="(item, index) in props.data" :data="item" :index="index" />
    </ul>
</template>

<style scoped>
</style>
