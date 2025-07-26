<script setup lang="js">
import { ref } from 'vue';


const name = ref('')
const changeName = function (event) {
  console.log("event", event);
  const inputValue = event.target.value;
  name.value = inputValue;
};



const users = ref([
  { id: 1, name: "John" },
  { id: 2, name: "Jane" },
  { id: 3, name: "Jim" },
]);

const addNewUser = function () {
  users.value.push({name:name.value, id:new Date().getTime()})
};
</script>
<template>
  <div>
    <!-- <p :id="counter">Counter: {{ counter }}</p>
    <h1>Hello {{ name }}</h1>
    <button @click="incCounter">Click me</button> -->
    <input type="text" v-bind:value="name" @input="changeName" />
    <button @click="addNewUser">Add new user</button>
    <p v-for="user in users" :key="user.id">
      {{ user.name }}
      {{ user.id }}
    </p>
  </div>
</template>
<style></style>
