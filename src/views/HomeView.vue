<template>
  <main>
    <div class="video-background-wrapper" v-if="!showWelcomePage">
      <video
        autoplay
        muted
        playsinline
        class="video-bg"
        @ended="onVideoEnded"
        @play="!showWelcomePage"
      >
        <source
          src="https://s3.eu-central-1.amazonaws.com/dreamlog.io/Dreamlog+Intro+2.mp4"
          type="video/mp4"
        />
      </video>
    </div>
    <TheWelcome v-if="showWelcomePage" />
  </main>
</template>

<script setup>
import { ref } from 'vue'
import TheWelcome from '../components/TheWelcome.vue'

const showWelcomePage = ref(true)

function onVideoEnded() {
  showWelcomePage.value = false
}
</script>

<style>
main {
  width: 100%;
  height: 100%;
}
.video-background-wrapper {
  position: relative;
  width: 100%;
  height: 100vh;
  overflow: hidden;
}

.video-bg {
  position: absolute;
  top: 50%;
  left: 50%;
  min-width: 100%;
  min-height: 100%;
  transform: translate(-50%, -50%);
  object-fit: cover;
  z-index: -1;
}
</style>
