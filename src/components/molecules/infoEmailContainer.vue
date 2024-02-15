<script setup>
</script>

<template>
    <div class="infoEmailContainer"><slot></slot></div>
</template>

<style>
    .infoEmailContainer {
        margin-top: 42px;
        margin-bottom: 24px;
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 0;
    }
    @media (min-width: 376px) {
        .infoEmailContainer {
            margin-bottom: 24px;
        }
    }
</style>
