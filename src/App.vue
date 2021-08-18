<template>
  <div id="app">
    <h1> Nest </h1>
    <img alt="Vue logo" src="./assets/logo.png">
    <HelloWorld subtitle="Monkey" msg="Welcome Paul Dixon"/>
    <h1> Nest </h1>
    <HelloWorld msg="Welcome Tom"/>
    <HelloWorld subtitle="Practice"/>
    <ShoppingList />
    <HelloWorld msg="Cat Images"/>
    <DefaultImages images="https://placekitten.com/200/140/"/>
    <DefaultImages images="https://placekitten.com/408/287" />
    <ListImages />
    <FootyScores />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ShoppingList from './components/ShoppingList.vue'
import DefaultImages from './components/DefaultImages.vue'
import ListImages from './components/ListImages.vue'
import FootyScores from './components/FootyScores.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    ShoppingList,
    DefaultImages,
    ListImages,
    FootyScores
  }
}
</script>

<style>
#app {
  display: flexbox;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  }
</style>
