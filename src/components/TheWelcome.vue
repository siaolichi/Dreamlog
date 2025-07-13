<script setup>
import bgImage from '@/assets/images/login-bg.png'
import LoginSection from './LoginSection.vue'
import WarningCard from './WarningCard.vue'
import { ref } from 'vue'

const submitted = ref(false)

function onSubmit() {
  submitted.value = true
}

function onClickCard() {
  submitted.value = false
}
</script>

<style>
.welcome {
  width: 100%;
  height: 100%;
  background-position: center;
  background-size: cover;
  display: flex;
  justify-content: center;
  align-items: center;
}
</style>

<template>
  <div class="welcome" :style="{ backgroundImage: `url(${bgImage})` }">
    <LoginSection @on-submit="onSubmit" />
    <WarningCard v-if="submitted" @on-click="onClickCard" />
  </div>
</template>
