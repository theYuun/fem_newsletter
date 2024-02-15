<script setup>
</script>

<template>
    <div class="signupDiv">
        <slot></slot>
    </div>
</template>

<style>
    .signupDiv {
        display: grid;
        grid-template-areas:
            "image"
            "info";
        margin-bottom: 34px;
        background-color: white;
    }

    @media (min-width: 376px) {
        .signupDiv {
            width: 930px;
            height: 640px;
            margin: 220px auto;
            grid-template-columns: 480px 1fr;
            grid-template-areas:
                "info image";
            border-radius: 34px;
        }
    }

</style>
