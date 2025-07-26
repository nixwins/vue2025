<script setup lang="ts">
// products list
const products = [{ id: 1, name: "Product 1", price: 100 }];
// Task 0: вывести список продуктов в виде ul>li(имя продукта, цена)
// Task 1: Add product добавить продукт в список
// Task 2: Delete product удалить продукт из списка
// Task 3: Sort products сортировать продукты по цене (js Array.sort)
</script>
<template>
  <div>
    <h1>Products</h1>
    <h5>Sort by price: <button>Asc</button></h5>
    <div>
      <input type="text" />
      <button>Add product</button>
    </div>
    <ul>
      <li>
        <span>Product 1</span>
        <span>100</span>
        <button>Delete</button>
      </li>
    </ul>
  </div>
</template>
<style scoped lang="scss"></style>
