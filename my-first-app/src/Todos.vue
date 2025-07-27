<script setup lang="js">
import { ref } from 'vue';

const todos = ref([
  {
    id: 1,
    name: 'Reading',
  },
])

const todoName = ref('')
function handleTodoName(event) {
  console.log("123", event)
  todoName.value = event.target.value
}

function addNewTodo() {
   todos.value.push({id:Math.random(), name: todoName.value})
}
</script>
<template>
  <div>
    <h1>{{ todoName }}</h1>
    <input type="text" @input="handleTodoName" />
    <button @click="addNewTodo">Add todo</button>
    <ul>
      <li v-for="item in todos" :key="item.id">
        {{ item.name }}
      </li>
    </ul>
  </div>
</template>
<style scoped lang="scss"></style>
