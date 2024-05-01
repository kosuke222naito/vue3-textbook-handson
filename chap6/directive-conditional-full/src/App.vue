<script setup lang="ts">
import { ref } from "vue";

const randomNumber = ref(Math.round(Math.random() * 100));
</script>

<template>
  <section>
    点数は{{ randomNumber }}点で、
    <span v-if="randomNumber >= 80">優です。</span>
    <span v-else-if="randomNumber >= 70">良です。</span>
    <span v-else-if="randomNumber >= 60">可です。</span>
    <span v-else>不可です。</span>
  </section>
</template>
