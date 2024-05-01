<script setup lang="ts">
import { ref } from "vue";

const inputNameBind = ref("しんちゃん");
const inputNameOn = ref("ななし");

const onInputName = (event: Event): void => {
  inputNameOn.value = (event.target as HTMLInputElement).value;
};
</script>

<template>
  <section>
    <input type="text" :value="inputNameBind" />
  </section>
  <br />
  <section>
    <input type="text" @input="onInputName" />
    <p>{{ inputNameOn }}</p>
  </section>
</template>
