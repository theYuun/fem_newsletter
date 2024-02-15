<script setup>
import atoms from './atoms';
const props = defineProps({
    data: {
        type: Array,
        required: true,
    }
})

const ListIndex = atoms.ListIndex;
</script>

<template>
    <ul>
        <ListIndex v-for="(item, index) in props.data" :data="item" :index="index" />
    </ul>
</template>

<style>
    ul {
        margin: 24px;
        list-style-type: none;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
</style>
