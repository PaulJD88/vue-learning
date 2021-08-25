<template>
  <div id="app">
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#cats">Cats</a></li>
      <li class="dropdown">
        <a href="javascript:void(0)" class="dropbtn">Football</a>
        <div class="dropdown-content">
          <a @click="getScores">Premier League Teams</a>
          <a href="#">Championship Teams</a>
          <a href="#">Division One Teams</a>
        </div>
      </li>
    </ul>
    <FootyScores />
  </div>
</template>

<script>
import FootyScores from "./components/FootyScores.vue";

export default {
  name: "App",
  components: {
    FootyScores,
  },
};
</script>

<style>
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #333;
}

li {
  float: left;
}

li a,
.dropbtn {
  display: inline-block;
  color: white;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

li a:hover,
.dropdown:hover .dropbtn {
  background-color: red;
}

li.dropdown {
  display: inline-block;
}

.dropdown-content {
  display: none;
  position: absolute;
  background-color: #f9f9f9;
  min-width: 160px;
  box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
  z-index: 1;
}

.dropdown-content a {
  color: black;
  padding: 12px 16px;
  text-decoration: none;
  display: block;
  text-align: left;
}

.dropdown-content a:hover {
  background-color: #f1f1f1;
}

.dropdown:hover .dropdown-content {
  display: block;
}
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
