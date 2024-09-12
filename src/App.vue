<template>
  <h1 class="todo-heading">TODOs</h1>
  <nav class="navigation">
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link>
  </nav>
  <HeaderComp />
  <router-view />
</template>

<script>
import HeaderComp from "./components/Header"
export default { components: [HeaderComp] }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

.navigation {
  margin-top: 5px;
  margin-bottom: 10px;
  padding: 0px;
}

.todo-heading {
  align-self: center;
  font-size: 50px;
  color: purple;
  margin-bottom: 0px;
  margin-top: 10px
}
</style>
