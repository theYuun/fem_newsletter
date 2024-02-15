<script setup>
const props = defineProps({
    path: {
        type: String,
        required: true,
    },
    altText: {
        type: String,
    }
})
</script>

<template>
    <img class="listIcon" :src="props.path" :alt="props.altText" :aria-label="`${props.altText}.`" />
</template>

<style>
    .listIcon {
        content: '';
        position: absolute;
        top: 2px;
        left: 0px;
        width: 21px;
        height: 21px;
    }
</style>
