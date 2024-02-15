<script setup>
</script>

<template>
    <div class="successSpacer">
        <slot></slot>
    </div>
</template>

<style>
    .successSpacer {
        flex: 1;
    }
    @media (min-width: 376px) {
        .successSpacer {
            margin: 0;
            padding: 0;
        }
    }
</style>
