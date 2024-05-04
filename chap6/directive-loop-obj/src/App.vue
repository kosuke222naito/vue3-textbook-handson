<script setup lang="ts">
import { ref } from "vue";

const whiteLadyInit: {
  id: number;
  name: string;
  price: number;
  recipe: string;
} = {
  id: 2345,
  name: "ホワイトレディ",
  price: 1200,
  recipe: "ジン、コアントロー、レモン汁",
};
const whiteLady = ref(whiteLadyInit);
</script>

<template>
  <dl>
    <template v-for="(value, key) in whiteLady" :key="key">
      <dt>{{ key }}</dt>
      <dt>{{ value }}</dt>
    </template>
  </dl>
</template>
