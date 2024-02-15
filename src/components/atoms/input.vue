<script setup>
import { ref, computed, defineEmits } from 'vue';

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
    },
    function: {
        type: Function,
    },
    data: Object,
})

const emits = defineEmits(['setStringsFromInput', 'emailErrorFromButton', 'emailSuccessFromButton', 'dismissSuccessFromButton']);

const inputStrings = ref({
    email: '',
});

function setStrings() {
    emits('setStringsFromInput', { type: 'email', value: inputStrings.value.email, });
}

const errorMessage = ref('');

const functions = {
    sendEmailAddress: () => {
        
        const emailRegex = /^[\w-]+(\.[\w-]+)*@([\w-]+\.)+[a-zA-Z]{2,7}$/;

        if(props.data.email.length <= 0)
        {
            errorMessage.value = 'Email required';
            console.log('emailError / errorMessage: ', errorMessage.value, ' @ input');
            emits('emailErrorFromButton', errorMessage.value)
        }
        else if(!emailRegex.test(props.data.email))
        {
            errorMessage.value = 'Valid email required';
            console.log('emailError / errorMessage: ', errorMessage.value, ' @ input');
            emits('emailErrorFromButton', errorMessage.value)
        }
        else {
            console.log('emailSuccess @ input');
            emits('emailSuccessFromButton');
        }
        
    },
    dismissSuccessDialog: () => {
        console.log('dismissSuccessDialog @ input');
        emits('dismissSuccessFromButton');
        console.log('emitted dismiss @ input');
    }
}

function executeFunction(functionName) {
    if(functions[functionName]) {
        functions[functionName]();
    }
    else {
        console.log(`Function ${functionName} does not exist.`)
    }
};

const exposedFunctions = computed(() => functions)
</script>

<template>
    <input
        v-if="props.type === 'email'"
        v-model="inputStrings.email"
        @input="setStrings"
        :type="props.type"
        :id="props.id"
        placeholder="email@company.com" />
    <input
        v-if="props.type === 'button'"
        @click="executeFunction(props.function)"
        :type="props.type"
        :value="props.buttonText" />
</template>

<style>
    input[type=email] {
        border-radius: 7.5px;
        border: 1px solid var(--colorDarkSlateGrey);
        margin-top: 11px;
        padding: 17px 23px 18px;
        font-size: 1rem;
        grid-column: span 2;
    }
    input[type=button] {
        width: 100%;
        border-radius: 7.5px;
        border: none;
        padding-top: 20px;
        padding-bottom: 17px;
        background-color: var(--colorDarkSlateGrey);
        text-align: center;
        font-family: "Roboto Bold";
        font-size: 1rem;
        color: #fff;
    }
    input[type=button]:hover {
        background: var(--buttonGradient);
        cursor: pointer;
    }
</style>
