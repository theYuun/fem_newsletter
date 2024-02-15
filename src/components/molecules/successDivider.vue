<script setup>
</script>

<template>
    <div class="successDivider">
        <slot></slot>
    </div>
</template>

<style>
    .successDivider {
        position: absolute;
        inset: 0;
        background-color: white;
        padding-top: 150px;
        padding-left: 24px;
        padding-right: 24px;
        display: flex;
        flex-direction: column;
    }
    @media (min-width: 376px) {
        .successDivider {
            width: 505px;
            height: 518px;
            margin-top: 60px;
            margin-left: calc(calc(100% - 505px) / 2);
            /*
            */
            padding: 0;
            border-radius: 34px;
        }
    }
</style>
