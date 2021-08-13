<template>
  <div class="hello">
    <h1>Picture List</h1>
    <ul>
      <li v-for="listImage in listed" :key="listImage">{{listImage}}</li>
      <img v-if="listed" :src=" listed ">
    </ul>
  </div>
</template>

<script>
export default {
  name: 'ListImages',
  data() {
    return {
      listed: ["https://placekitten.com/408/287", "https://placekitten.com/200/139", "https://placekitten.com/200/287"]
    }
  }
}
</script>

<style scoped>
ul {
color: purple;
}
</style>
