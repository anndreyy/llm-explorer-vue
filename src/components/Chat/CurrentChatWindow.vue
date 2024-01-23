<script>
import MessageInputField from './MessageInputField.vue'
import { ref, onMounted } from 'vue';

export default {
    components: { MessageInputField },
    setup() {
        const htmlContent = ref(''); // Deve ser definida dentro do setup para ser reativa

        async function fetchHtmlContent(path) {
            try {
                const response = await fetch(path);
                return await response.text();
            } catch (error) {
                console.error('Failed to load HTML content', error);
            }
        }

        onMounted(async () => {
            const htmlFilePath = 'src\\components\\Chat\\ChatHistory.html'; // O caminho para o seu arquivo HTML
            htmlContent.value = await fetchHtmlContent(htmlFilePath);
        });

        // O objeto retornado aqui pode ser usado no template
        return {
            htmlContent
        };
    },
}
</script>

<template>
    <div class="border">
        <!-- Use "htmlContent" diretamente, já que está definido como uma propriedade reativa -->
        <div v-html="htmlContent" class="chat-history-html"></div>

        <MessageInputField class="message-input-field" />
    </div>
</template>
<style lang="scss"></style>