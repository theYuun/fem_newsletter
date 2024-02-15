<script setup>
const props = defineProps({
    text: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <h1 class="dismissHeading">{{ props.text }}</h1>
</template>

<style scoped>
    .dismissHeading {
        margin-top: 39px;
        font-size: 2.4rem;
        letter-spacing: 0.75px;
        font-family: 'Roboto Bold';
        line-height: 40px;
    }
</style>
