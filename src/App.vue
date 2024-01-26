<script setup>
import { RouterLink, RouterView } from 'vue-router'
import ButtonDarkMode from './components/Commons/ButtonDarkMode.vue'
</script>

<template>
  <!-- Cabeçalho -->
  <header class="chat-header">
    <div class="sidea">
      <figure><img src="./assets/icons/logo.png"></figure>
      <h1>LLM Explorer</h1>
    </div>
    <div class="sideb">
      <div class="container-language">
        <button class="selected">EN</button>
        <button >ES</button>
        <button >PT-BR</button>
      </div>
      <ButtonDarkMode />
    </div>
  </header>
  <div class="container">
    <RouterView />
  </div>
</template>

<style scoped></style>
