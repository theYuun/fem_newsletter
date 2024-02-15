<script setup>
const props = defineProps({
    text: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <h1 class="infoHeading">{{ props.text }}</h1>
</template>

<style scoped>
    .infoHeading {
        font-size: 2.4rem;
        letter-spacing: 0.75px;
        font-family: 'Roboto Bold';
    }
</style>
