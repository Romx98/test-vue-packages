<script setup lang="ts">
import { ref } from "vue";

const inputText = ref<string>("");
const headerText = ref<string>("");

function updateHeader(): void {
  headerText.value = inputText.value;
}
</script>

<template>
  <div class="container">
    <input
      v-model="inputText"
      type="text"
      class="input-text"
      placeholder="Enter text"
    />
    <button
      @click="updateHeader"
      class="btn"
    >
      Update Header
    </button>
    <h1 class="header">{{ headerText }}</h1>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  height: 100vh;
}

.input-text {
  padding: 10px;
  font-size: 16px;
  border: 1px solid var(--color-border);
  border-radius: 4px;
  margin-bottom: 10px;
  width: 300px;
  color: var(--color-text);
  background: var(--color-background-soft);
}

.input-text::placeholder {
  color: var(--color-text);
}

.input-text:focus {
  outline: none;
  border-color: var(--color-border-hover);
}

.btn {
  padding: 10px 20px;
  font-size: 16px;
  color: var(--vt-c-white);
  background-color: var(--vt-c-indigo);
  border: none;
  border-radius: 4px;
  cursor: pointer;
  transition: background-color 0.3s;
}

.btn:hover {
  background-color: var(--vt-c-indigo-light);
}

.header {
  margin-top: 20px;
  color: var(--color-heading);
}
</style>
