<template>
  <div id="app">
    <Tabletop />
  </div>
</template>

<script>
import Tabletop from './components/Tabletop'

export default {
  name: 'App',
  components: {
    Tabletop
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
