<template>
  <div id="app">
    <img id="logo" alt="Vue logo" src="./assets/logo.png">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <tabla />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Tabla from './components/Tabla.vue'

export default {
  name: 'App',
  components: {
    // HelloWorld
    Tabla
  }
}
</script>

<style scope>
/* #app { */
#logo {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
}
</style>
