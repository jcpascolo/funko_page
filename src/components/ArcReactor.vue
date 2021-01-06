<template>
  <div class="arc-reactor__circle" :class="{ open: isOpen }">
    <div class="arc-reactor__inner-circle center"></div>
    <div class="arc-reactor__triangle center"></div>
    <div class="arc-reactor__inner-triangle center"></div>
  </div>
</template>

<script>
export default {
  props: {
    isOpen: Boolean
  }

}
</script>

<style>
.arc-reactor__circle {
  width: 200px;
  height: 200px;
  border: 4px solid #132a47;
  border-radius: 50%;
  background-color: #f9ffff;
  position: relative;
  filter: drop-shadow(0 0 10px var(--logo-glow-color));
  animation: lightning 5s infinite;
}

.arc-reactor__circle.open {
  animation: none;
}

.arc-reactor__inner-circle {
  width: 175px;
  height: 175px;
  border-radius: 50%;
  background-color: #132a47;
}

.arc-reactor__triangle {
  width: 180px;
  height: 180px;
  background-color: #f9ffff;
  clip-path: polygon(14% 15%, 86% 15%, 96% 30%, 60% 99%, 40% 99%, 4% 30%);
}

.arc-reactor__inner-triangle {
  width: 100px;
  height: 100px;
  background-color: #132a47;
  clip-path: polygon(14% 15%, 86% 15%, 96% 30%, 60% 99%, 40% 99%, 4% 30%);
}

@keyframes lightning {
  0%,
  100% {
    filter: drop-shadow(0 0 10px var(--logo-glow-color));
  }
  50% {
    filter: drop-shadow(0 0 75px var(--logo-glow-color));
  }
}
</style>