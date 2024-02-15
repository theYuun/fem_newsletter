<script setup>
import { ref, defineEmits, defineProps } from 'vue';
import atoms from '../atoms/atoms';
import molecules from '../molecules/molecules';

const props = defineProps({
    listData: {
        type: Array,
    }
})

const emits = defineEmits(['emailSuccessFromInfoSection']);

const InfoDivider = molecules.InfoDivider;
const InfoHeading1 = molecules.InfoHeading;
const InfoParagraph = molecules.InfoParagraph;
const InfoList = molecules.InfoList;
const InfoEmailContainer = molecules.InfoEmailContainer;
const Label = atoms.Label;
const Span = atoms.Span;
const Input = atoms.Input;

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
    <InfoDivider>
        <InfoHeading1
            :text="'Stay updated!'" />
        <InfoParagraph
            :text="'Join 60,000+ product managers receiving monthly updates on:'" />
        <InfoList
            :data="props.listData" />
        <InfoEmailContainer>
            <Label
                :text="'Email address'"
                :labelFor="'emailInput'" />
            <Span
                v-show="emailError"
                :text="errorMessage.email" />
            <Input
                :type="'email'"
                @setStringsFromInput="setStrings"
                :placeholder="'email@company.com'"
                :id="'emailInput'" />
            
        </InfoEmailContainer>
        <!--
            Possible function for :function prop on :type="'button'":
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
    </InfoDivider>
</template>

<style>
</style>
