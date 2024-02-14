<script setup>
import { ref, defineProps, defineEmits } from 'vue';

const props = defineProps({
    email: {
        type: String,
        required: true,
    }
})

const emits = defineEmits(['dismissSuccessFromSuccessDialog'])

import atoms from '../atoms/atoms';
import molecules from '../molecules/molecules';

const SuccessDivider = molecules.SuccessDivider;
const Image = atoms.Image;
const Heading1 = atoms.Heading1;
const Paragraph = atoms.Paragraph;
const Input = atoms.Input;

function dismissSuccess() {
    console.log('dismissSuccess @ dialogSuccess')
    emits('dismissSuccessFromSuccessDialog')
}

</script>

<template>
    <SuccessDivider>
        <Image :path="'/fem_newsletter/images/icon-success.svg'" :altText="'Success!'" />
        <Heading1 :text="'Thanks for subscribing!'" />
        <Paragraph :text="`A confirmation email has been sent to ${props.email}. Please open it and click the button to confirm your subscription.`" />
        <Input
            :type="'button'"
            :function="'dismissSuccessDialog'"
            @dismissSuccessFromButton="dismissSuccess"
            :buttonText="'Dismiss message'" />
    </SuccessDivider>
</template>

<style scoped>
</style>
