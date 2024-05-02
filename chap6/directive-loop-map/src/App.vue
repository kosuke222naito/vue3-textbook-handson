<script setup lang="ts">
import { ref } from "vue";

const cocktailsInit = new Map<number, string>();
cocktailsInit.set(2345, "ホワイトレディ");
cocktailsInit.set(4412, "ブルーハワイ");
cocktailsInit.set(6792, "ニューヨーク");
const cocktails = ref(cocktailsInit);
</script>

<template>
  <ul>
    <li v-for="[id, cocktailName] in cocktails" :key="id">
      IDが{{ id }}のカクテルは{{ cocktailName }}
    </li>
  </ul>
</template>
