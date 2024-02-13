<script setup>
import atoms from '../atoms/atoms';

const Divider = atoms.Divider;
const Heading1 = atoms.Heading1;
const Paragraph = atoms.Paragraph;
const Label = atoms.Label;
const List = atoms.List;
const Input = atoms.Input;
</script>

<template>
    <Divider>
        <Heading1 :text="'Stay updated!'" />
        <Paragraph :text="'Join 60,000+ product managers receiving monthly updates on:'" />
        <List :data="['Product discovery and building what matters', 'Measuring to ensure updates are a success', 'And much more!']" />
        <Label :text="'Email Address'" :labelFor="'emailInput'" />
        <Input :type="'email'" :placeholder="'email@company.com'" :id="'emailInput'" />
        <Input :type="'button'" :buttonText="'Subscribe to monthly newsletter'" />
    </Divider>
</template>

<style scoped>
</style>
