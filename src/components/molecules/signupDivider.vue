<script setup>
</script>

<template>
    <div class="signupDiv">
        <slot></slot>
    </div>
</template>

<style scoped>
    .signupDiv {
        position: relative;
        display: grid;
        grid-template-areas: 
        "image"
        "info";
        margin-bottom: 34px;
    }

    @media (min-width: 376px) {
        .contentDiv {
            grid-template-areas: 
            "info image";
        }
    }

</style>
