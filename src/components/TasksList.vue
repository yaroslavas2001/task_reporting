<template>
    <div v-for="item, index in tasksList" :key="index" class="block">
        <div class="wrapper">
            <div class="title_wrapper">
                <div>
                    {{ item.title }}
                </div>
                <div class="time_wrapper">
                    <div> {{ item.timeFrom }} - {{ item.timeTo }}</div>
                    <div>
                        <button @click="edit(item.id)">edit</button>
                        <button @click="dalete(item.id)">delete</button>
                    </div>
                </div>
            </div>
            <div class="description">{{ item.description }}</div>
        </div>
    </div>
</template>
<script setup>
import { ref } from 'vue'

defineProps({
    tasksList: Array,
    curentTask: String
})
const emit = defineEmits(['edit', 'dalete'])

function edit(id) {
    emit('edit', id)
}
function dalete(id) {
    emit('dalete', id)
}
</script>
  
<style scoped>
.block {
    margin: 10px 0px;
    border-radius: 8px;
    overflow: hidden;
}

.wrapper {
    border-left: 5px solid black;
    padding: 5px 20px;
    border-radius: 10px;
}

.title_wrapper {
    display: flex;
    align-items: center;
}

.time_wrapper {
    display: flex;
    align-items: center;
    padding: 0px 20px;
}

.description {
    text-align: left;
}
</style>
  