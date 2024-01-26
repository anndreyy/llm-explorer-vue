<template>
    <div class="chat-settings-sidebar">

        <div class="form">
            <h1 class="font-weight-medium">Settings</h1>
            <form @submit.prevent="submitForm">
                <div class="form-group">
                    <label for="llm" class="form-label">LLM Family</label>
                    <select id="llm" v-model="form.llm" required class="form-control">
                        <option value="">Please select an option</option>
                        <option value="Gemini">Gemini</option>
                        <option value="llm2">GPT4</option>
                        <option value="llm3">GPT3.5</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="model" class="form-label">Model</label>
                    <select id="model" v-model="form.model" required class="form-control">
                        <option value="">Please select an option</option>
                        <option value="Gemini PRO">Gemini PRO</option>
                        <option value="model2">GPT 4</option>
                        <option value="model3">GPT 4 Turbo</option>
                        <option value="model3">GPT 3.5 Turbo</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="temperature" class="form-label">Temperature</label>
                    <input type="number" id="temperature" v-model.number="form.temperature" min="0.0" max="0.9" step="any" required class="form-control">
                </div>

                <div class="form-group">
                    <label for="base" class="form-label">Knowledgebase</label>
                    <select id="base" v-model="form.base" @change="checkForFileImport" required class="form-control">
                        <option value="">Please select an option</option>
                        <option value="option1">Corporativo</option>
                        <option value="option2">Option 2</option>
                        <option value="import">Import File</option>
                    </select>
                </div>

                <div v-if="showFileInput" class="form-group">
                    <input type="file" @change="handleFileUpload" class="form-control">
                </div>

                <div class="form-group">
                    <label for="initialPrompt" class="form-label">Initial Prompt</label>
                    <textarea id="initialPrompt" v-model="form.initialPrompt" required class="form-control">Default value</textarea>
                </div>

            </form>
        </div>

    </div>
</template>
  
<script setup>
import { ref } from 'vue';

const form = ref({
    llm: 'Gemini',
    model: 'Gemini PRO',
    temperature: 0.7,
    base: 'option1'
});

const showFileInput = ref(false);

const checkForFileImport = () => {
    showFileInput.value = form.value.base === 'import';
};

const handleFileUpload = (event) => {
    // Handle the file upload logic here
    console.log(event.target.files[0]);
};

const submitForm = () => {
    // Submit form logic here
    console.log(form.value);
};
</script>
  
<style scoped>
.chat-settings-sidebar .form-group {
    margin-bottom: 1rem;
}

.chat-settings-sidebar label {
    display: block;
    margin-bottom: .5rem;
}

.chat-settings-sidebar input,
.chat-settings-sidebar select,
.chat-settings-sidebar button {
    width: 100%;
    padding: .5rem;
    font-size: 1rem;
}

.chat-settings-sidebar button {
    margin-top: 1rem;
}
</style>
  