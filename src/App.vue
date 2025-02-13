<template>
  <div class="background">
    <BackGround />
  </div>
  <div class="navbar fixed top-0 w-full z-50">
    <NavBar />
  </div>
  <div class="main">
    <TheHome />
    <TheAbout />
  </div>
  <div><TheFooter /></div>
</template>

<script setup>
import NavBar from './components/NavBar.vue'
import TheHome from './components/HeroSection.vue'
import TheFooter from './components/TheFooter.vue'
import TheAbout from './components/TheAbout.vue'
import BackGround from './components/BackGround.vue'
</script>

<style scoped>
.background {
  position: relative;
  z-index: -1;
}
</style>
