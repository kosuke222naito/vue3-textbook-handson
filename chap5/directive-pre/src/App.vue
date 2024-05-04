<script setup lang="ts">
import { ref } from "vue";

const hello = ref("hello");
const showHello = (): void => {
  alert(hello.value);
};
</script>

<template>
  <section v-pre>
    <!-- なぜか@clickにするとうまくレンダリングされない -->
    <p v-on:click="showHello">{{ hello }}</p>
  </section>
</template>
