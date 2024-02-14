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

<style scoped>
</style>
