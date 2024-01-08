<template>
  <!-- <HelloWorld msg="Vite + Vue" /> -->
  <TasksList :tasks-list="tasksList" :curent-task="curentTask" @edit="edit" @dalete="dalete" />
  <ProjectDetails />
</template>

<script setup>
import { ref } from 'vue'
import TasksList from './components/TasksList.vue'
import ProjectDetails from './components/ProjectDetails.vue'
const tasksList = ref([
  {
    id: '24',
    title: 'Test title',
    description: 'test description',
    timeFrom: '13:10',
    timeTo: '14:30'
  },
  {
    id: '14',
    title: 'Test title',
    description: 'test description',
    timeFrom: '13:10',
    timeTo: '14:30'
  }
])
const curentTask = '24'
function edit(id) {
  console.log('edit', id)
}
function dalete(id) {
  console.log('delete', id)
  tasksList.value = [
    {
      id: '24',
      title: 'Test title',
      description: 'test description',
      timeFrom: '13:10',
      timeTo: '14:30'
    }
  ]
}
</script>



<style scoped></style>
