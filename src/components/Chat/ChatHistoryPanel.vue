<template>
    <div>
        <div class="group-btn">
            <button role="button" class="btn normal">
                <span class="text">New Chat</span>
            </button>
        </div>

        <div class="history-chats">
            <ul>
                <li>
                    <div class="llm">GPT4</div>
                    <div class="message">Nanotecnologia</div>
                </li>
                <li>
                    <div class="llm">Gemini Pro</div>
                    <div class="message">Forecast 2024</div>
                </li>
                <li>
                    <div class="llm">Llama2</div>
                    <div class="message">Escreva um e-mail...</div>
                </li>
            </ul>
        </div>
    </div>
</template>
<script setup>
import IconPlus from '../icons/IconPlus.vue';
</script>