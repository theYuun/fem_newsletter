<script setup>
import { ref } from 'vue';
import organisms from '../organisms/organisms';
import molecules from '../molecules/molecules';

const SignupDivider = molecules.SignupDivider;
const Image = molecules.ImageSectionImage;
const InformationSection = organisms.InfrmationSection;
const SuccessSection = organisms.SuccessSection;

const emailSuccess = ref(false);
const stringInputs = ref({
    email: '',
})
const listData = ref([
    'Product discovery and building what matters',
    'Measuring to ensure updates are a success',
    'And much more!'])

function setEmailSuccess(data) {
    console.log('emailSuccess @ signup')
    stringInputs.value[data.type] = data.value;
    emailSuccess.value = true;
    console.log('emailSuccess: ', emailSuccess.value, ' @ signup')
}
function dismissEmailSuccess() {
    console.log('dismissEmailSuccess @ signup')
    emailSuccess.value = false;
    console.log('emailSuccess: ', emailSuccess.value, ' @ signup')
}

</script>

<template>
    <SignupDivider>
        <Image
            :pathMobile="'/fem_newsletter/images/illustration-sign-up-mobile.svg'"
            :pathFull="'/fem_newsletter/images/illustration-sign-up-desktop.svg'"
            :altText="''" />
        <InformationSection
            @emailSuccessFromInfoSection="setEmailSuccess"
            :listData="listData" />
    </SignupDivider>
    <!--
        // This is here in case I need to temp remove the `v-if`
        // of the SuccessSection
    -->
    <SuccessSection
        v-show="emailSuccess"
        @dismissSuccessFromSuccessDialog="dismissEmailSuccess"
        :email="stringInputs.email" />
</template>

<style>
</style>
