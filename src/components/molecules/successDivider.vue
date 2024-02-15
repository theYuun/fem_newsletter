<script setup>
</script>

<template>
    <div class="successDivider">
        <slot></slot>
    </div>
</template>

<style scoped>
    .successDivider {
        position: absolute;
        inset: 0;
        background-color: white;
        padding: 0 24px;
        padding-top: 150px;
        display: flex;
        flex-direction: column;
    }
</style>
