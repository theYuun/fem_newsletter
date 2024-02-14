<script setup>
import { ref, defineEmits } from 'vue';
import atoms from '../atoms/atoms';

const emits = defineEmits(['emailSuccessFromInfoSection']);

const Divider = atoms.Divider;
const Heading1 = atoms.Heading1;
const Paragraph = atoms.Paragraph;
const Label = atoms.Label;
const List = atoms.List;
const Input = atoms.Input;
const Span = atoms.Span;

const inputStrings = ref({
    email: '',
})

const setStrings = (data) => {
    console.log('setStrings: ', data, ' @ infoSection')
    inputStrings.value[data.type] = data.value;
    console.log('setStrings: ', inputStrings.value, ' @ infoSection')
}

const emailError = ref(false);
const errorMessage = ref({
    email: '',
})
const emailSuccess = ref(false);

function setEmailError(message) {
    console.log('setEmailError @ infoSection');
    console.log(message);
    emailError.value = true;
    emailSuccess.value = false;
    errorMessage.value.email = message;
}
function setEmailSuccess() {
    console.log('setEmailSuccess @ infoSection');
    emailError.value = false;
    emailSuccess.value = true;
    errorMessage.value.email = '';
    emits('emailSuccessFromInfoSection', { type: 'email', value: inputStrings.value.email});
}


</script>

<template>
    <Divider>
        <Heading1 :text="'Stay updated!'" />
        <Paragraph :text="'Join 60,000+ product managers receiving monthly updates on:'" />
        <List :data="['Product discovery and building what matters', 'Measuring to ensure updates are a success', 'And much more!']" />
        <Divider>
            <Label :text="'Email Address'" :labelFor="'emailInput'" />
            <Span v-if="emailError" :text="errorMessage.email" />
            <Input :type="'email'" @setStringsFromInput="setStrings" :placeholder="'email@company.com'" :id="'emailInput'" />
            <!--
                Possible function for function prop:
                'sendEmailAddress'
                'dismissSuccessDialog'
             -->
    
            <Input
                :type="'button'"
                :function="'sendEmailAddress'"
                :data="inputStrings"
                @emailErrorFromButton="(data) => setEmailError(data)"
                @emailSuccessFromButton="setEmailSuccess"
                :buttonText="'Subscribe to monthly newsletter'" />
        </Divider>
    </Divider>
</template>

<style scoped>
</style>
