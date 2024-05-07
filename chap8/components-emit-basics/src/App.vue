<script setup lang="ts">
import { ref } from "vue";
import OneSection from "./components/OneSection.vue";

const randomNumberInit = Math.round(Math.random() * 10);
const randomNumber = ref(randomNumberInit);

const updateRandomNumber = (): void => {
  randomNumber.value = Math.round(Math.random() * 10);
};
</script>

<template>
  <section>
    <p>親コンポーネントで乱数を表示: {{ randomNumber }}</p>
    <OneSection :randomNumber @onUpdateRandomNumberButtonClick="updateRandomNumber" />
  </section>
</template>
