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

<style>
    .infoHeading {
        font-size: 2.4rem;
        letter-spacing: 0.75px;
        font-family: 'Roboto Bold';
    }
    @media (min-width: 376px) {
        .infoHeading {
            font-size: 3.4rem;
        }
    }
</style>
