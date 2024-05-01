<script setup lang="ts">
import { ref, computed } from "vue";

const number = ref(80);
const isShown = computed((): boolean => {
  return !Math.round(Math.random());
});
</script>

<template>
  <p v-if="number >= 50">(1): (常に)表示される</p>
  <p v-if="Math.round(Math.random()) >= 0.5">(2): 表示されることもある</p>
  <p v-if="isShown">(3): 表示されることもある</p>
</template>
