<script setup>
import ChatHistoryPanel from '../components/Chat/ChatHistoryPanel.vue'
import CurrentChatWindow from '../components/Chat/CurrentChatWindow.vue'
import ChatSettingsSidebar from '../components/Chat/ChatSettingsSidebar.vue'
</script>

<template>
  <div class="chat-container">
    <!-- Cabeçalho -->
    <header class="chat-header">
      <h1>LLM Explorer</h1>
    </header>

    <!-- Corpo Principal -->
    <!-- Painel de histórico de chats -->
    <chat-history-panel class="chat-history" />

    <!-- Janela de chat atual -->
    <current-chat-window class="current-chat" />

    <!-- Painel de configurações -->
    <chat-settings-sidebar class="chat-settings" />

  </div>
</template>
<style scoped></style>
