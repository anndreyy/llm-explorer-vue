<script setup>
import { RouterLink, RouterView } from 'vue-router'

</script>

<template>
  <!-- Cabeçalho -->
  <header class="chat-header">
    <h1>LLM Explorer</h1>
  </header>
  <div class="conteiner">
    <RouterView />
  </div>
</template>

<style scoped></style>
