<script setup lang="ts">
import { ref } from "vue";

const message = ref("未送信");
const onFormSubmit = (): void => {
  message.value = "送信されました。";
};
</script>

<template>
  <form action="#" @submit.prevent="onFormSubmit">
    <input type="text" required />
    <button type="submit">送信</button>
  </form>
  <p>{{ message }}</p>
</template>
