<script setup>
</script>

<template>
    <div class="infoDivider"><slot></slot></div>
</template>

<style>
    .infoDivider {
        grid-area: info;
        margin-top: 12px;
        padding: 24px;
        padding-right: 16px;
    }
    @media (min-width: 376px) {
        .infoDivider {

        }
    }
</style>
