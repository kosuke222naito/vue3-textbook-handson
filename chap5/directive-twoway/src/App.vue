<script setup lang="ts">
import { ref } from "vue";

const inputName2Way = ref("しんちゃん");
const onInputName2Way = (event: Event): void => {
  inputName2Way.value = (event.target as HTMLInputElement).value;
};
</script>

<template>
  <section>
    <input type="text" :value="inputName2Way" @input="onInputName2Way" />
    <p>{{ inputName2Way }}</p>
  </section>
</template>
