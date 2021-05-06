<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/icon-jd.png">
    <h1>Ejemplo de Consumo get - Axios</h1>
    <EAxio />
  </div>
</template>

<script>
import EAxio from './components/EAxio.vue'

export default {
  name: 'App',
  components: {
    EAxio
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
