<script setup>
const props = defineProps({
  items: {},
  title: {},
});

const emit = defineEmits(["delete", "hoverItem"]);
console.log(props.items);
</script>

<template>
  <h1>{{ title }}</h1>
  <ul>
    <li
      v-for="item in items"
      :key="item.id"
      :class="{ old: item.age > 18 }"
      @mouseover="emit('hoverItem', item.id)"
    >
      <p>{{ item.name }}</p>
      <p v-if="item.age > 18">Age: {{ item.age }}</p>
      <button @click="emit('delete', item.id)">Delete</button>
    </li>
  </ul>
</template>

<style scoped>
ul {
  list-style-type: none;
  padding: 0;
  margin: 0;
}

li {
  padding: 10px;
  background-color: #f0f0f0;
  margin-bottom: 5px;
  border-radius: 5px;
}

.old {
  background-color: #000;
  color: #fff !important;
}
</style>
