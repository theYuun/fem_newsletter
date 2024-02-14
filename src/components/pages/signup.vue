<script setup>
import { ref } from 'vue';
import organisms from '../organisms/organisms';
import molecules from '../molecules/molecules';

const SignupDivider = molecules.SignupDivider;
const ImageSection = organisms.ImageSection;
const InformationSection = organisms.InfrmationSection;
const DialogSuccess = organisms.Success;

const emailSuccess = ref(false);
const stringInputs = ref({
    email: '',
})

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
        <ImageSection />
        <InformationSection @emailSuccessFromInfoSection="setEmailSuccess" />
    </SignupDivider>
    <DialogSuccess v-show="emailSuccess" @dismissSuccessFromSuccessDialog="dismissEmailSuccess" :email="stringInputs.email" />
</template>

<style scoped>
</style>
