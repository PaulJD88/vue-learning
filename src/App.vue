<template>
  <div id="app">
    <FootyScores />
  </div>
</template>

<script>
import FootyScores from './components/FootyScores.vue'

export default {
  name: 'App',
  components: {
    FootyScores
  }
}
</script>

<style>
#app {
  display: flex;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  justify-content: center;
  color: #2c3e50;
  width: 100%;
  }
</style>
