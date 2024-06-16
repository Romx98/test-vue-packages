<script setup lang="ts">
import { ref } from "vue";

const inputText = ref("");
const headerText = ref("");

function updateHeader() {
  headerText.value = inputText.value;
}
</script>

<template>
  <div>
    <input
      v-model="inputText"
      type="text"
    />
    <button @click="updateHeader">Update Header</button>
    <h1>{{ headerText }}</h1>
  </div>
</template>
