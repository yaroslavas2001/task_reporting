<template>
    <div>{{ label }}</div>
    <input v-model="innerValue" @change="changeValue"/>
</template>
<script setup>
import { ref } from 'vue'

const props = defineProps({
    label: String,
    modelValue: String
})
const emit = defineEmits(['update:modelValue'])
const innerValue = ref(props.modelValue)
function changeValue() {
    emit('update:modelValue', innerValue.value)
}

</script>
   