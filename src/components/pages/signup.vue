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
            :path="'/fem_newsletter/images/illustration-sign-up-mobile.svg'"
            :altText="''" />
        <InformationSection
            @emailSuccessFromInfoSection="setEmailSuccess"
            :listData="listData" />
    </SignupDivider>
    <!--
        v-show="emailSuccess"
    -->
    <SuccessSection
        @dismissSuccessFromSuccessDialog="dismissEmailSuccess"
        :email="stringInputs.email" />
</template>

<style scoped>
</style>
