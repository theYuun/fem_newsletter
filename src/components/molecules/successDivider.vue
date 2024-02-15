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
        padding-top: 150px;
        padding-left: 24px;
        padding-right: 16px;
        display: flex;
        flex-direction: column;
    }
</style>
