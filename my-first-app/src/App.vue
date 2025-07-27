<script setup lang="js">
import Todos from './Todos.vue';
import { ref } from 'vue';

const count = ref(0)
console.log(count)

const increment = function() {
  console.log('increment')
  count.value = count.value + 1
}

const imgSrc = ref('https://shared.fastly.steamstatic.com/store_item_assets/steam/apps/730/capsule_616x353.jpg?t=1749053861')
const users = ref([
  {
    id: 1,
    name: 'John',
    age: 20
  },
  {
    id: 2,
    name: 'Jane',
    age: 21
  },
  {
    id: 3,
    name: 'Jim',
    age: 22
  }
])
</script>
<template>
  <div class="container">
    <Todos />
    <ul>
      <li v-for="user in users" :key="user.id">
        {{ user.name }} - {{ user.age }}
      </li>
    </ul>

    <p id="counter">Счётчик: {{ count }}</p>
    <button id="incrementBtn" @click="increment">Увеличить</button>
    <h1 :id="count">Hello World</h1>
    <img v-bind:src="imgSrc" />
  </div>
</template>
<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
