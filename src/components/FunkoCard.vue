<template>
  <div class="funko-card">
    <Cube />
  </div>  
</template>

<script>
import Cube from './Cube.vue'
export default {
  name: 'FunkoCard',
  components: {
    Cube
  },
  props: {
    name: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.funko-card {
  padding: 15px;
  width: 250px;
  height: 300px;
}

.funko-card img {
  max-width: 100%;
  max-height: 100%;
}

</style>
