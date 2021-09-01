<template>
  <div id="app">
    <Weather />
    <Books />
  </div>


</template>

<script>


import Weather from './components/Weather.vue'
import Books from './components/Books.vue'

export default {
  name: 'app',
  components: {
    Weather, Books
    
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
