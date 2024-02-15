<script setup>
import molecules from '../molecules/molecules';
const props = defineProps({
    data: {
        type: String,
        required: true,
    },
    index: {
        type: String,
    }
})
const InfoListImage = molecules.InfoListImage;
</script>

<template>
    <li class="infoListIndex"><InfoListImage :src="'/fem_newsletter/images/icon-list.svg'" />{{ props.data }}</li>
</template>

<style scoped>
    .infoListIndex {
        padding-left: 37px;
        line-height: 1.5rem;
        position: relative;
    }
</style>
