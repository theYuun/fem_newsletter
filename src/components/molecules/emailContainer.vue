<script setup>
</script>

<template>
    <div class="emailInputContainer"><slot></slot></div>
</template>

<style scoped>
    .emailInputContainer {
        margin: 0 24px;
        margin-top: 42px;
        display: grid;
        grid-template-columns: 1fr 1fr;
        grid-template-rows: auto auto;
        gap: 0;
    }
</style>
