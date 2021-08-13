<template>
  <div class="container">
    <img v-if="images" :src=" images "> 
  <div class="overlay">
    <div class="text">A Cat</div>
  </div>
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
.container {
  border: dotted black;
  position: relative;
  width: 100%;
}

img {
  display: block;
  width: 100%;
  height: auto;
  border-radius: 10px;
}

.overlay {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  width: 100%;
  height: auto;
  opacity: 0;
  transition: .8s ease;
  background-color: #008CBA;
  border-radius: 10px;
}

.container:hover .overlay {
  opacity: 1;
}

.text {
  color: white;
  font-size: 20px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  -ms-transform: translate(-50%, -50%);
}
</style>
