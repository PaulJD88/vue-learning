<template>
  <div class="hello">
    <h1>Cat Images</h1>
    <img v-if="image">- {{ image }} - <img>
  </div>
</template>

<script>
export default {
  name: 'CatImage',
  data() {
    return {
      image: src=("https://placekitten.com/200/300")
    }
  }
}
</script>

<style scoped>
ul {
border: solid;
color: red;
}
</style>

    <ul>
      <li v-for="listItem in list" :key="listItem">{{listItem}}</li>
    </ul>