<template>
  <h1>{{ header ? header.toLocaleUpperCase() : "Welcome chloe" }}</h1>
  <input v-model.trim="newItem" type="text" placeholder="Add an item">
  <label>
    <input type="checkbox" v-model="newItemHighPriority">High Priority
  </label>
  <br>
  {{ newItem }} {{ newItemHighPriority }}
  <ul>
    <li v-for="({id, label}, index) in items" :key="id">{{ index }}: {{ label }}</li>
  </ul>
</template>

<script>
export default {
  name: "ShoppingList.vue",
  data() {
    return {
      header: 'Shopping List App',
      newItem: '',
      newItemHighPriority: false,
      items: [
        {id: 1, label: "10 bracelets"},
        {id: 2, label: "1 box of fruit punch"},
        {id: 3, label: "20 goody bags"}
      ]
    };
  }
}
</script>

<style scoped>

</style>