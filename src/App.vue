<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link> |
      <router-link to="/favorites">Favorites</router-link>
    </div>
    <router-view/>
    <footer class="footer">
      <p class="footer-partner-name">Mitchell McCann and Jarod Thorley</p>
      <a class="footer-link" href="https://github.com/mccannmann/creative-3/tree/mitchell-creative-3" target="_blank">Github</a>
    </footer>
  </div>
</template>

<style>

* {
  margin: 0;
}
body{
  background-color: #d4eeff;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #2c3e50;
  font-size: 30px;
}

#nav a.router-link-exact-active {
  color: #5879ef;
}

.footer-link {
  color: black;
  text-decoration: none;
  padding-right: 30px
}

.footer-link:hover {
  color: #bbbbbb;
  text-decoration: none;
}

.footer-link:active {
  color: #dddddd;
  text-decoration: none;
}

.footer {
  position: fixed;
  bottom: 0;
  background-color: #3879ef !important;
  width: 100%;
  height: 2.5rem;            /* Footer height */
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.footer-partner-name {
  margin-top: 0;
  margin-bottom: 0;
  margin-left: 20px;
  margin-right: 0;
}
</style>
