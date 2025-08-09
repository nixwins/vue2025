<script setup lang="js">
import ListItem from './ListItem.vue'
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
    age:17
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

const products = ref([
  {
    id: 1,
    name: 'Product 1',
    price: 100
  },

])

const isLoggedIn = ref(false)
const status = ref('success')

const deleteUser = (id) => {
  console.log(id)
  users.value = users.value.filter((user) => user.id !== id)
}

const addClass = (id) => {
  console.log(id)
}
</script>
<template>
  <div class="container">
    <ListItem
      :items="users"
      title="Users"
      @delete="deleteUser"
      @hoverItem="addClass"
      <hr
    />
    <ListItem :items="products" />
    <header>
      <button
        v-if="!isLoggedIn"
        class="btn"
        :class="{ loading: status === 'loading' }"
      >
        Login
      </button>
      <button v-else>Avatar</button>
      <p
        class="status"
        :class="['status-pending', { 'status-success': status === 'success' }]"
      >
        {{ status }}
      </p>
    </header>
    <Todos />
    <ul>
      <li v-for="user in users" :key="user.id">
        {{ user.name }} - {{ user.age }}
      </li>
    </ul>
    <ul>
      <li v-for="product in products" :key="product.id">
        {{ product.name }} - {{ product.price }}
      </li>
    </ul>

    <p id="counter">Счётчик: {{ count }}</p>
    <button id="incrementBtn" @click="increment">Увеличить</button>
    <h1 :id="count">Hello World</h1>
    <img v-bind:src="imgSrc" />
  </div>
</template>
<style>
.status {
  color: red;
}
.status-pending {
  color: blue;
}
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
.btn {
  background-color: #007bff;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 5px;
}

.loading {
  background-color: #6c757d;
}
</style>
