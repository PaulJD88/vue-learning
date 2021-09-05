<template>
  <div id="app">
    <div>
      <ul>
        <li><router-link to="/">Home</router-link></li>
        <li><router-link to="/cats">Cat Pictures</router-link></li>
        <li class="dropdown">
          <a class="dropbtn">Football</a>
          <div class="dropdown-content">
            <router-link to="/prem-league">Premier League Teams</router-link>
            <router-link to="/team-stats">Team Statistics</router-link>
          </div>
        </li>
      </ul>
    </div>
    <div>
      <router-view />
    </div>
  </div>
</template>

<style>
body {
  margin: 0;
}
ul {
  display: flex;
  align-content: space-between;
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #8c8c8c;
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
  background-color: #a64f03;
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
  background-image: linear-gradient(
    to bottom right,
    #02732a,
    white,
    #a2a633,
    white
  );
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
