<script setup>
import bgImage from '@/assets/images/login-bg.png'
</script>

<style>
.welcome {
  width: 100%;
  height: 100%;
  background-position: center;
  background-size: cover;
}
</style>

<template>
  <div class="welcome" :style="{ backgroundImage: `url(${bgImage})` }"></div>
</template>
