<script setup lang="ts">
import { ref } from "vue";

const isShown = ref(!Math.round(Math.random()));
</script>

<template>
  <section>
    v-ifを使用
    <p v-if="isShown">条件に合致したので表示</p>
  </section>
  <section>
    v-showを使用
    <p v-show="isShown">条件に合致したので表示</p>
  </section>
</template>
