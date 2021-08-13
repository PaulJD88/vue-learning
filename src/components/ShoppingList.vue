<template>
  <div class="hello">
    <h1>Shopping List</h1>
    <ul>
      <li v-for="listItem in list" :key="listItem">{{listItem}}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ShoppingList',
  data() {
    return {
      list: ["Carrots", "Garlic", "Chocolate", "Ice Cream"]
    }
  }
}
</script>

<style scoped>
ul {
color: red;
}
</style>

