<script setup>
import { ref, computed, watchEffect, watch, onMounted, onUnmounted } from 'vue';
const props = defineProps({
    pathMobile: {
        type: String,
        required: true,
    },
    pathFull: {
        type: String,
        required: true,
    },
    altText: {
        type: String,
    }
})

const isMobile = ref(window.innerWidth < 376);

const windowInnerWidth = ref(376);

function UpdateWindowInnerWidth() {
    windowInnerWidth.value = window.innerWidth;
    if(windowInnerWidth.value < 376)
        isMobile.value = true;
    else
        isMobile.value = false;
}

UpdateWindowInnerWidth();

onMounted(() => {
    window.addEventListener('resize', UpdateWindowInnerWidth)
})

onUnmounted(() => {
    window.removeEventListener('resize', UpdateWindowInnerWidth)
})

</script>

<template>
    <img v-if="isMobile" class="signupImageMobile" :src="props.pathMobile" :alt="props.altText" :aria-label="`${props.altText}.`" />
    <img v-if="!isMobile" class="signupImageFull" :src="props.pathFull" :alt="props.altText" :aria-label="`${props.altText}.`" />
</template>

<style>
    .signupImageMobile, .signupImageFull {
        grid-area: image;
        width: calc(100% + 9px);
        margin: 0;
        padding: 0;
    }

    .signupImageFull {
        margin: 26px;
        width: calc(100% - 52px);
    }
</style>
