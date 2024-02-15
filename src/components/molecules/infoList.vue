<script setup>
import molecules from '../molecules/molecules';

const props = defineProps({
    data: {
        type: Array,
        required: true,
    }
})

const InfoListIndex = molecules.InfoListIndex;
</script>

<template>
    <ul class="infoList">
        <InfoListIndex
            v-for="(item, index) in props.data"
            :data="item"
            :index="index" />
    </ul>
</template>

<style>
    .infoList {
        margin-top: 24px;
        list-style-type: none;
        display: flex;
        flex-direction: column;
        gap: 10px;
    }
</style>
