<script setup>
import { RouterLink, RouterView } from 'vue-router'
import ButtonDarkMode from './components/Commons/ButtonDarkMode.vue'
</script>

<template>
  <!-- Cabeçalho -->
  <header class="chat-header">
    <div>
      <h1>LLM Explorer</h1>
    </div>
    <div>
      <ButtonDarkMode />
    </div>
  </header>
  <div class="container">
    <RouterView />
  </div>
</template>

<style scoped></style>
