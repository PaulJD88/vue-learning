<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h3 v-if="subtitle">- {{ subtitle }} -</h3>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
    subtitle: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  margin: 40px 0 0;
  color: red;
}
h3 {
  color: purple;
}
</style>
