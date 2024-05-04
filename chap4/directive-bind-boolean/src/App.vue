<script setup lang="ts">
import { ref } from "vue";

const isSendButtonDisabled = ref(false);

setInterval(() => {
  isSendButtonDisabled.value = Math.random() < 0.5;
}, 1000);
</script>

<template>
  <p><button :disabled="isSendButtonDisabled">送信</button></p>
</template>
