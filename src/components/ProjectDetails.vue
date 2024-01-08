<template>
    <div>
        <div>Project details </div>
        yourName : {{ yourName }}
        Project name: {{ ProjectName }}
        <LabelInput label="Your name" v-model="yourName" />
        <LabelInput label="Project name" v-model="ProjectName" />
        <div>
            <button>Settings</button>
            <button>Print</button>
        </div>
    </div>
</template>
<script setup>
import LabelInput from './LabelInput.vue'
import { ref } from 'vue'

const yourName = ref('6456')
const ProjectName = ref('34535')


</script>
  
<style scoped></style>
  