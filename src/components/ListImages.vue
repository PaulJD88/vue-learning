<template>
  <div class="hello">
    <h1>Picture List</h1>
    <img v-for="image in images" :key="image" :src="image">
    <img v-for="x in images" :key="x" :src="x">
  </div>
</template>

<script>
export default {
  name: 'ListImages',
  data() {
    return {
      images: [
        "https://placekitten.com/408/286", 
        "https://placekitten.com/200/139", 
        "https://placekitten.com/200/287"
      ]
    }
  }
}
</script>

<style scoped>
ul {
color: purple;
}
</style>
