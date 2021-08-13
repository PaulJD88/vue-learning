<template>
  <div class="hello">
    <img v-if="images" :src=" images "> 
  </div>
</template>

<script>
export default {
  name: 'DefaultImages',
  props: {
    images: String,
  }
}
</script>

<style scoped>
img {
border: 1px solid black;
border-radius: 8px;
padding: 5px;
max-width: 100%;
height: auto;
}
</style>
