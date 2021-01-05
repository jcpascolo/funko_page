<template>
  <div id="app">
    <FunkoCard name="Venomized" color="#aa0505"/>
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
@font-face {
  font-family: "IronMan";
  src: local("IronMan"),
    url("./assets/fonts/ironman_war.ttf") format("truetype");
}

</style>
