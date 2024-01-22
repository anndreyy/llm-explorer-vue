
<template>
    <div>
        <textarea 
            v-model="promptTextArea"
            @input="autoExpand"
            name="promptTextArea" 
            id="promptTextArea" 
            rows="1"
            placeholder="Mensagem"
            >
        </textarea>
        <button>
            <IconSendVue />
        </button>

    </div>
</template>
<script setup>
import IconSendVue from '../icons/IconSend.vue';
import { ref } from 'vue';

const promptTextArea = ref('');

const autoExpand = (event) => {
  event.target.style.height = 'inherit';
  // Calcula a altura
  const computed = window.getComputedStyle(event.target);
  const height = parseInt(computed.getPropertyValue('border-top-width'), 10)
                 + event.target.scrollHeight
                 + parseInt(computed.getPropertyValue('border-bottom-width'), 10);
  
  event.target.style.height = `${height}px`;
};
</script>