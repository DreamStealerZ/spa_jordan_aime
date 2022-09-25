<template>
  <div id="app">
    <router-link to="/">Home</router-link><br>
    <router-view></router-view>
  </div>
</template>

<script>

export default {
  name: 'App',
}
</script>

<style>
#app {
  font-family: Ubuntu, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

table {
  border-collapse: separate;
  border-spacing: 10px 30px;
}

.table>:not(caption)>*>* {
  padding: none;
  background-color: none;
  box-shadow: none;
}

.vignette {
  font-size: 0;
  background-color: brown !important;
  border-radius: 50%;
  width: 50px;
  height: 50px;
  text-align: center;
  vertical-align: middle;
  padding: 15px;
}

.vignette::first-letter {
  font-size: 1rem;
  color: white;
  text-transform: capitalize;
  font-weight: bold;
}

.titre {
  color: grey;
  font-weight: bold;
}

.titre::first-letter {
  text-transform: capitalize;
}
</style>
