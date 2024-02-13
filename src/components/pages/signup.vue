<script setup>
import organisms from '../organisms/organisms';
import molecules from '../molecules/molecules';

const SignupDivider = molecules.SignupDivider;
const ImageSection = organisms.ImageSection;
const InformationSection = organisms.InfrmationSection;
const DialogSuccess = organisms.Success;
</script>

<template>
    <SignupDivider>
        <ImageSection />
        <InformationSection />
    </SignupDivider>
    <DialogSuccess />
</template>

<style scoped>
</style>
