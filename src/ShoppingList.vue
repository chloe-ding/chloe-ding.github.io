<template>
  <h1>{{ header ? header.toLocaleUpperCase() : "Welcome chloe" }}</h1>

  <div class="add-item-form">
    <input
        @keyup.enter="saveItem"
        v-model.trim="newItem" type="text" placeholder="Add an item">
    <label>
      <input type="checkbox" v-model="newItemHighPriority">High Priority
    </label>
    <button
      @click="saveItem"
      class="btn btn-primary">
      Save Item
    </button>
  </div>



<!--  <br>-->
<!--  {{ newItem }} {{ newItemHighPriority }}-->

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
    }
  },

  methods: {
    saveItem() {
      this.items.push({id: this.items.length + 1, label: this.newItem});
      this.newItem = "";
    }
  }
}
</script>

<style scoped>

</style>