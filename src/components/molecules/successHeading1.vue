<script setup>
const props = defineProps({
    text: {
        type: String,
        required: true,
    }
})
</script>

<template>
    <h1 class="successHeading">{{ props.text }}</h1>
</template>

<style>
    .successHeading {
        margin-top: 39px;
        font-size: 2.4rem;
        letter-spacing: 0.75px;
        font-family: 'Roboto Bold';
        line-height: 40px;
    }
    @media (min-width: 376px) {
        .successHeading {
            margin: 0 64px;
            margin-top: 38px;
            font-size: 3.45rem;
            letter-spacing: 0.45px;
            line-height: 58px;
        }
    }
</style>
