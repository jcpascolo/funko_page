<template>
  <div id="app">
    <FunkoCard name="Venomized"/>
  </div>
</template>

<script>
import FunkoCard from './components/FunkoCard.vue'

export default {
  name: 'App',
  components: {
    FunkoCard
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
  background-color: #2c3e50;
}
</style>
