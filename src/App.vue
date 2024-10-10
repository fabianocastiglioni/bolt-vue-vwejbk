<script setup lang="ts">
import LandingPage from './components/LandingPage.vue'
import LoginPage from './components/LoginPage.vue'
import { ref } from 'vue'

const showLogin = ref(false)

const toggleLogin = () => {
  showLogin.value = !showLogin.value
}
</script>

<template>
  <div class="app-container">
    <LandingPage v-if="!showLogin" @login="toggleLogin" />
    <LoginPage v-else @back="toggleLogin" />
  </div>
</template>

<style>
.app-container {
  max-width: 800px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}
</style>