<template>
  <div class="funko-card" @mouseenter="mouseenter" @mouseleave="mouseleave">
    <div class="funko-card__image" :style="'background-color: ' + this.color">
      <Cube class="funko-card__image-cube" :color="this.color" :isActive="this.isHover"/>
      <div class="funko-card__clip-path"><span class="iron-font">{{this.name}}</span></div>
    </div>
    <div class="funko-card__name">
      <span class="iron-font">{{this.name}}</span>          
    </div>  
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
    name: String,
    color: String
  },
  data() {
    return {
      isHover: false,
      hasLeave: false
    }
  },
  methods: {
    mouseenter: function(){
      this.hasLeave ? this.hasLeave = false : this.hasLeave = false;
      setTimeout(() => {
        !this.hasLeave ? this.isHover = true : this.hasLeave = false;
      }, 1500);    
    },    
    mouseleave: function(){
      this.isHover = false;
      this.hasLeave = true;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.funko-card {
  width: 225px;
  height: 220px;
  border-radius: 10px;
  position: relative;
}

.funko-card__image {
  display: flex;
  align-items: center;
  position: relative;
  min-height: 220px;
  justify-content: center;
  border-top-right-radius: 10px;
  border-bottom-left-radius: 10px;
  z-index: 1;
  transition: all 0.2s linear;
}

.funko-card:hover .funko-card__image{
  min-height: 230px;
  align-items: center;
}

.funko-card__image-cube {
  transition: transform 0.7s linear;
  transition-delay: 0.7s;
}

.funko-card:hover .funko-card__image .funko-card__image-cube {
  transform: scale(0.8);
}

.funko-card__name {
  width: 225px;
  height: 60px;
  margin-top: -60px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: black;
  color: white;
  border-bottom-left-radius: 10px;
  transition: margin-top 0.3s linear;
  transition-delay: 0s;
}

.funko-card__name span {
  padding-top: 12px;
  font-size: 24px;
}

.funko-card:hover .funko-card__name {
  margin-top: -10px;
  transition-delay: 0.7s;
}

.funko-card__clip-path {
  background-color: black;
  position: absolute;
  display: flex;
  justify-content: center;
  align-items: flex-end;
  color: white;
  padding-bottom: 10px;
  bottom: 0px;
  z-index: 3;
  height: 150px;
  width: 225px;
  border-bottom-left-radius: 10px;
  clip-path: polygon(0 74%, 100% 58%, 100% 100%, 0% 100%);
  transition: clip-path 0.5s linear;
  transition-delay: 0.2s;
}

.funko-card__clip-path span {
  padding-bottom: 4px;
  font-size: 20px;
  transform: rotateZ(-5deg);
}

.funko-card:hover .funko-card__image .funko-card__clip-path {
  clip-path: polygon(0 100%, 100% 100%, 100% 100%, 0% 100%);
}
</style>
