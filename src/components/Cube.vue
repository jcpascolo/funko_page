<template>
  <div class="container">
    <div id="cube" :class="{ active: isActive }">
      <div class="front"><img src="../assets/images/venomized/png_1_front.png" alt="Ironman Venomized front"></div>
      <div class="back"><img src="../assets/images/venomized/png_3_back.png" alt="Ironman Venomized back"></div>
      <div class="left"><img src="../assets/images/venomized/png_4_right.png" alt="Ironman Venomized right"></div>
      <div class="right"><img src="../assets/images/venomized/png_2_left.png" alt="Ironman Venomized left"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cube',
  props: {
    name: String
  },
  data() {
    return {
      isActive: true
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.container {
  width: 150px;
  height: 200px;
  position: relative;
  -webkit-perspective: 1000px;
  -moz-perspective: 1000px;
}

#cube {
  width: 100%;
  height: 100%;
  position: absolute;
  -webkit-transform-style: preserve-3d;  
  -moz-transform-style: preserve-3d;
}

#cube img {
  max-width: 137px;
  max-height: 183px;
  display: block;
  position: absolute;
  top: 7px;
  left: 6px;
  border: none;
  background-color: #2c3e50;
}

.active {   
  -webkit-animation: rotatecube 15s infinite linear;
  -moz-animation: rotatecube 15s infinite linear;
}

@-webkit-keyframes rotatecube {
  from{
    -webkit-transform: rotateX(0deg) rotateY(360deg) rotateZ(0deg);
  }
  to {
    -webkit-transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg);
  }
  /* 0% { -webkit-transform: rotateX(0deg) rotateY(360deg) rotateZ(0deg); }
  25% { -webkit-transform: rotateX(0deg) rotateY(270deg) rotateZ(0deg); }
  50% { -webkit-transform: rotateX(0deg) rotateY(180deg) rotateZ(0deg); }
  75% { -webkit-transform: rotateX(0deg) rotateY(90deg) rotateZ(0deg); }
  100% { -webkit-transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg); } */
}

@-moz-keyframes rotatecube {
  from{
    -moz-transform: rotateX(0deg) rotateY(360deg) rotateZ(0deg);
  }
  to {
    -moz-transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg);
  }
  /* 0% { -moz-transform: rotateX(0deg) rotateY(360deg) rotateZ(0deg); }
  25% { -moz-transform: rotateX(0deg) rotateY(270deg) rotateZ(0deg); }
  50% { -moz-transform: rotateX(0deg) rotateY(180deg) rotateZ(0deg); }
  75% { -moz-transform: rotateX(0deg) rotateY(90deg) rotateZ(0deg); }
  100% { -moz-transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg); } */
}


#cube .front  {
  -webkit-transform: rotateY(0deg ) translateZ( 68px );
  -moz-transform: rotateY( 0deg ) translateZ( 68px );
}
#cube .back {
  display: none;
  -webkit-transform: translateZ( -68px );
  -moz-transform: translateZ( -68px );
}
#cube .right  {
  display: none;
  -webkit-transform: rotateY(  90deg ) translateZ( 68px );
  -moz-transform: rotateY(  90deg ) translateZ( 68px );
}
#cube .left   {
  display: none;
  -webkit-transform: rotateY( -90deg ) translateZ( 68px );
  -moz-transform: rotateY( -90deg ) translateZ( 68px );
}

#cube.active .back  {
  display: block;
}
#cube.active .right {
  display: block;
}
#cube.active .left {
  display: block;
}
</style>
