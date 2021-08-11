<template>
  <div id="app">
    <h1> Nest </h1>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld subtitle="Monkey" msg="Welcome Paul Dixon"/>
    <h1> Nest </h1>
    <HelloWorld msg="Welcome Tom"/>
    <ShoppingList />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ShoppingList from './components/ShoppingList.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ShoppingList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
