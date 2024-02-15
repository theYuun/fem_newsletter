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
const SuccessImage = molecules.SuccessImage;
const SuccessHeading1 = molecules.SuccessHeading;
const SuccessParagraph = molecules.SuccessParagraph;
const SuccessSpacer = molecules.SuccessSpacer;
const SuccessButtonContainer = molecules.SuccessButtonContainer;
const Input = atoms.Input;

function dismissSuccess() {
    console.log('dismissSuccess @ dialogSuccess')
    emits('dismissSuccessFromSuccessDialog')
}

</script>

<template>
    <SuccessDivider>
        <SuccessImage
            :path="'/fem_newsletter/images/icon-success.svg'"
            :altText="'Success!'" />
        <SuccessHeading1
            :text="'Thanks for subscribing!'" />
        <SuccessParagraph
            :text="`A confirmation email has been sent to ${props.email}. Please open it and click the button to confirm your subscription.`" />
        <SuccessSpacer />
        <SuccessButtonContainer>
            <Input
                :type="'button'"
                :function="'dismissSuccessDialog'"
                @dismissSuccessFromButton="dismissSuccess"
                :buttonText="'Dismiss message'" />
        </SuccessButtonContainer>
    </SuccessDivider>
</template>

<style scoped>
</style>
