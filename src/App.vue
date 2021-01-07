<template>
  <div id="app">
    <div class="landing-page fullpage" >
      <div class="left-side fullpage" :class="{'open': this.isOpen}">
        <h1 class="iron-font">IRON</h1>
      </div>      
      <ArcReactor class="logo center" :class="{'open': this.isOpen}" v-on:click.native="openLanding" :isOpen="this.isOpen"/>      
      <div ref="rightSide" class="right-side fullpage" :class="{'open': this.isOpen}">
        <h1 class="iron-font">MAN</h1>
      </div>
    </div>
    <div class="funko-page fullpage">
      <FunkoCard v-for="funko in funkos" 
        :key="funko.id" 
        class="funko-page__funko-card" 
        :id="funko.id" 
        :name="funko.name" 
        :color="funko.color"
      />
    </div>    
  </div>
</template>

<script>
import FunkoCard from './components/FunkoCard.vue'
import ArcReactor from './components/ArcReactor.vue'

export default {
  name: 'App',
  components: {
    FunkoCard,
    ArcReactor
  },
  data() {
    return {
      isOpen: false,
      funkos: [
        {
          id: 1,
          name: "venomized",
          color: "#aa0505"
        },
        {
          id: 2,
          name: "hulkbuster",
          color: "#fbca03"
        },
        {
          id: 3,
          name: "i am ironman",
          color: "#b97d10"
        },
        {
          id: 4,
          name: "gameverse",
          color: "#aa0505"
        },
        {
          id: 5,
          name: "glove",
          color: "#fbca03"
        },
        {
          id: 6,
          name: "wings",
          color: "#b97d10"
        },
      ]
    }
  },
  methods: {
    openLanding() {
      this.isOpen = !this.isOpen      
    }
  }
}
</script>

<style>
@font-face {
  font-family: "IronMan";
  src: local("IronMan"),
    url("./assets/fonts/ironman_war.ttf") format("truetype");
}

:root {
  --metal-black: rgb(30, 25, 25);
  --metal-dark-red: #6a0c0b;
  --metal-red: #aa0505;
  --metal-yellow: #fbca03;
  --metal-orange: #b97d10;
  --logo-glow-color: #01cbfead;
}

*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  height: 100vh;
  width: calc(100vw - (100vw - 100%));
  position: relative;
}

.fullpage {
  height: 100%;
  width: 100%;
}

.center {
  position: absolute;
  margin-left: auto;
  margin-right: auto;
  margin-top: auto;
  margin-bottom: auto;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  text-align: center;
}

.iron-font {
  font-family: "IronMan";
}

.landing-page {
  position: relative;
  overflow: hidden;
}

.right-side {
  background-color: var(--metal-yellow);
  color: var(--metal-red);
  position: absolute;
  z-index: 2;
  clip-path: polygon(0 99%, 100% 0, 100% 100%, 0 100%);
  display: flex;
  justify-content: flex-end;
  align-items: center;
  transition: transform 2s linear;
}

.right-side.open {
  transform: translateX(100vw);
}

.left-side {
  background-color: var(--metal-red);
  color: var(--metal-yellow);
  position: absolute;
  z-index: 2;
  clip-path: polygon(0 0, 100% 0%, 0 100%, 0% 100%);
  display: flex;
  justify-content: flex-start;
  align-items: center;
  transition: transform 2s linear;
}

.left-side.open {
  transform: translateX(-100vw);
}

.left-side h1, .right-side h1 {
  width: calc(50% - 100px);
  text-align: center;
  position: relative;
  font-size: 125px;
  height: 95px;
}

.left-side h1 {
  text-align: right;
  padding-right: 32px;
}

.right-side h1 {
  text-align: left;
  padding-left: 32px;
}  

.logo {
  z-index: 3;
  cursor: pointer;
  transition: transform 1s linear;
  transition-delay: 1s;
}

.logo.open {
  transform: translateX(-50vw);
  transition: transform 1s linear;
}

.funko-page {
  position: absolute;
  overflow: scroll;
  top: 0;
  left: 0;
  z-index: 1;
  padding: 10px 10px 10px 125px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
  background-color: var(--metal-black);
}

.funko-page__funko-card {
  min-height: 280px;
  margin: 0px 12px 20px 12px;
}


@media (max-width: 1199.98px) {  
  .left-side h1 {
    padding-right: 10px;
  }

  .right-side h1 {
    padding-left: 10px;
  } 
}

@media (max-width: 991.98px) {
  .left-side h1 {
    padding-right: 6px;
  }

  .right-side h1 {
    padding-left: 6px;
  } 
}

@media (max-width: 767.98px) {
  .funko-page {
    padding: 10px 10px 10px 75px;
  }

  .logo.open {
    transform: translateX(-60vw);
  }

  .left-side h1, .right-side h1 {
    font-size: 110px;
    height: 85px;
  }
}

@media (max-width: 575.98px) {
  .left-side h1, .right-side h1 {
    width: 75%;
  }

  .right-side {
    align-items: flex-end;
    padding-bottom: calc((50vh - 100px)/4);
  }

  .left-side {
    align-items: flex-start;
    padding-top: calc((50vh - 100px)/4);
  }
}

</style>
