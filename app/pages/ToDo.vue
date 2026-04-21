<template>
  <div>
    <h1>Todo App</h1>
    <v-card>
      <v-data-table :items="todos" :headers="headers"></v-data-table>
    </v-card>
  </div>
</template>

<script setup>

const headers = [
  { title: 'ID:', key: 'id'},
  { title: 'Title:', key: 'title'},
  { title: 'Status:', key: 'completed'}
]
const todos = ref([])

const getTodos = async() => {
  const data =  await $fetch('https://jsonplaceholder.typicode.com/todos')
  console.log(data)
  todos.value = data

}

onMounted(() => {
  getTodos();
})
</script>
<style>
</style>