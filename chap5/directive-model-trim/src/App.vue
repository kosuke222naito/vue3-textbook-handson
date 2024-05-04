<script setup lang="ts">
import { ref } from "vue";

const trimedText = ref("");
const rawText = ref("");
</script>

<template>
  <section>
    <input type="text" v-model="rawText" />
    <p>入力文字列: {{ trimedText }}</p>
    <input type="text" v-model.trim="trimedText" />
    <p>入力文字列: {{ trimedText }}</p>
  </section>
</template>
