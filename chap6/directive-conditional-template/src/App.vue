<script setup lang="ts">
import { ref } from "vue";

const randomNumber = ref(Math.round(Math.random() * 100));
</script>

<template>
  <p>
    点数は{{ randomNumber }}点
    <template v-if="randomNumber >= 80">
      で優です。
      <span class="textRed">素晴らしい！</span>
    </template>
  </p>
</template>

<style>
.textRed {
  color: red;
}
</style>
