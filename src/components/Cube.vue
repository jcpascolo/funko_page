<template>
  <div class="container">
    <div id="cube" :class="{ active: isActive }">
      <div class="front"><img src="../assets/images/venomized/1_front.jpg" alt="Ironman Venomized front"></div>
      <div class="back"><img src="../assets/images/venomized/3_back.jpg" alt="Ironman Venomized back"></div>
      <div class="left"><img src="../assets/images/venomized/2_left.jpg" alt="Ironman Venomized left"></div>
      <div class="right"><img src="../assets/images/venomized/4_right.jpg" alt="Ironman Venomized right"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cube',
  props: {
    color: String,
    isActive: Boolean
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

.container {
  width: 116px;
  height: 160px;
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
  display: block;
  position: absolute;
  border: none;
}

#cube .front img, #cube .back img {
  width: 116px;
  height: 160px;
  max-width: 116px;
  max-height: 160px;
}

#cube .left img, #cube .right img {
  width: 90px;
  height: 160px;
  max-width: 90px;
  max-height: 160px;
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
    -webkit-transform: rotateX(0deg) rotateX(0deg) rotateZ(0deg);
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
  -webkit-transform: translateZ( 45px );
  -moz-transform: translateZ( 45px );
}
#cube .back {
  display: none;
  -webkit-transform: translateZ( -45px );
  -moz-transform: translateZ( -45px );
}
#cube .right  {
  display: none;
  -webkit-transform: rotateY(  90deg ) translateX(13px) translateZ( 58px );
  -moz-transform: rotateY(  90deg ) translateX(13px) translateZ( 58px );
}
#cube .left   {
  display: none;
  -webkit-transform: rotateY( -90deg ) translateX(13px) translateZ( 58px );
  -moz-transform: rotateY( -90deg ) translateX(13px) translateZ( 58px );
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
