<script setup lang="ts">
import { ref } from "vue";

const randomNumberDisplayInit = "まだです";
const randomNumberDisplay = ref(randomNumberDisplayInit);
const onButtonClick = (): void => {
  randomNumberDisplay.value = String(Math.round(Math.random() * 10));
};
const onButtonDoubleClick = (): void => {
  if (randomNumberDisplay.value === randomNumberDisplayInit) return;
  randomNumberDisplay.value = String(parseInt(randomNumberDisplay.value) * 2);
};
</script>

<template>
  <section>
    <button @click="onButtonClick">クリック!</button>
    <button @dblclick="onButtonDoubleClick">ダブルクリック!!</button>
    <p>結果: {{ randomNumberDisplay }}</p>
  </section>
</template>
