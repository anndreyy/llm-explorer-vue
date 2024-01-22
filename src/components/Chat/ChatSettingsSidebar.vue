<template>
    <div class="chat-settings-sidebar">

        <div class="form">
            <h2>Settings</h2>
            <form @submit.prevent="submitForm">
                <div class="form-group">
                    <label for="llm">LLM</label>
                    <select id="llm" v-model="form.llm" required>
                        <option value="">Please select an option</option>
                        <option value="llm1">LLM 1</option>
                        <option value="llm2">LLM 2</option>
                        <option value="llm3">LLM 3</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="model">Model</label>
                    <select id="model" v-model="form.model" required>
                        <option value="">Please select an option</option>
                        <option value="model1">Model 1</option>
                        <option value="model2">Model 2</option>
                        <option value="model3">Model 3</option>
                    </select>
                </div>

                <div class="form-group">
                    <label for="temperature">Temperature</label>
                    <input type="number" id="temperature" v-model.number="form.temperature" min="0" step="any" required>
                </div>

                <div class="form-group">
                    <label for="base">Base</label>
                    <select id="base" v-model="form.base" @change="checkForFileImport" required>
                        <option value="">Please select an option</option>
                        <option value="option1">Option 1</option>
                        <option value="option2">Option 2</option>
                        <option value="import">Import File</option>
                    </select>
                </div>

                <div v-if="showFileInput" class="form-group">
                    <input type="file" @change="handleFileUpload">
                </div>

                <div class="form-group">
                    <label for="initialPrompt">Initial Prompt</label>
                    <textarea id="initialPrompt" v-model="form.initialPrompt" required>Default value</textarea>
                </div>

            </form>
        </div>

    </div>
</template>
  
<script setup>
import { ref } from 'vue';

const form = ref({
    llm: '',
    model: '',
    temperature: 0,
    base: ''
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
  