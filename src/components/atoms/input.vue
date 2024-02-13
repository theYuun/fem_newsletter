<script setup>
const props = defineProps({
    label: {
        type: String,
        required: true,
    },
    type: {
        type: String,
    },
    buttonText: {
        type: String,
    },
    id: {
        type: String,
    }
})
</script>

<template>
    <input v-if="props.type === 'email'" :type="props.type" :id="props.id" placeholder="email@company.com" />
    <input v-if="props.type === 'button'" :type="props.type" :value="props.buttonText" />
</template>

<style scoped>
</style>
