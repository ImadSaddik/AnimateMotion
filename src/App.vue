<template>
  <section class="container">
    <img class="illustration" :src="illustrationSrc" alt="A solar system with planets orbiting around the sun" />
    <button class="custom-button" @click="toggleAnimation">{{ buttonText }}</button>
  </section>
</template>

<script>
import animatedSolarSystemSVG from "@/assets/solar_system_animated.svg";
import staticSolarSystemSVG from "@/assets/solar_system_static.svg";

export default {
  name: "App",
  computed: {
    buttonText() {
      return this.showAnimatedSVG ? "Stop animation" : "Start animation";
    },
    illustrationSrc() {
      return this.showAnimatedSVG ? this.animatedSolarSystemSVG : this.staticSolarSystemSVG;
    },
  },
  data() {
    return {
      animatedSolarSystemSVG,
      staticSolarSystemSVG,
      showAnimatedSVG: false,
    };
  },
  methods: {
    toggleAnimation() {
      this.showAnimatedSVG = !this.showAnimatedSVG;
    },
  },
};
</script>

<style>
#app {
  font-family: "Inter", Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

  width: 100%;
}

body {
  margin: 0;
  padding: 0;
  background: #01030e;
}

.container {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.illustration {
  width: 40%;
}

.custom-button {
  position: absolute;
  bottom: 20px;
  left: 20px;
  padding: 10px 20px;
  background-color: #f97316;
  color: black;
  border: none;
  cursor: pointer;
  font-size: 16px;
  font-weight: 600;
}
</style>
