<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <ListView></ListView>
  </div>
</template>

<script>
import ListView from './components/List.vue'
export default {
  name: 'app',
  components: {
    ListView
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
