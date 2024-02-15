<script setup>
</script>

<template>
    <div class="successButtonContainer">
        <slot></slot>
    </div>
</template>

<style>
    .successButtonContainer {
        margin-bottom: 60px;
    }
    @media (min-width: 376px) {
        .successButtonContainer {
            margin: 0 64px;
            margin-bottom: 62px;
        }
    }
</style>
