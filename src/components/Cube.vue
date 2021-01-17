<template>
  <div class="container">
    <div id="cube" :class="{ active: isActive }">
      <div class="front"><img loading="lazy" :src="require(`@/assets/images/${this.foldername}/1_front.jpg`)" :alt="`Ironman ${this.name} front`"></div>
      <div class="back"><img loading="lazy" :src="require(`@/assets/images/${this.foldername}/3_back.jpg`)" :alt="`Ironman ${this.name} back`"></div>
      <div class="left"><img loading="lazy" :src="require(`@/assets/images/${this.foldername}/2_left.jpg`)" :alt="`Ironman ${this.name} left`"></div>
      <div class="right"><img loading="lazy" :src="require(`@/assets/images/${this.foldername}/4_right.jpg`)" :alt="`Ironman ${this.name} right`"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Cube',
  props: {
    name: String,
    color: String,
    isActive: Boolean
  },
  data() {
    return {
      foldername: this.name.split(" ").join("_")
    }
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
  -webkit-animation: rotatecube 12s infinite linear;
  -moz-animation: rotatecube 12s infinite linear; 
  -webkit-animation-delay: 0.5s;
  -moz-animation-delay: 0.5s;
}

@-webkit-keyframes rotatecube {
  from{
    -webkit-transform: rotateX(0deg) rotateY(360deg) rotateZ(0deg);
  }
  to {
    -webkit-transform: rotateX(0deg) rotateX(0deg) rotateZ(0deg);
  }
}

@-moz-keyframes rotatecube {
  from{
    -moz-transform: rotateX(0deg) rotateY(360deg) rotateZ(0deg);
  }
  to {
    -moz-transform: rotateX(0deg) rotateY(0deg) rotateZ(0deg);
  }
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
