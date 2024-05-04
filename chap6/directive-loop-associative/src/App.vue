<script setup lang="ts">
import { ref } from "vue";

const cocktailsInit: { [key: number]: string } = {
  2345: "ホワイトレディ",
  4412: "ブルーハワイ",
  6792: "ニューヨーク",
};

const cocktails = ref(cocktailsInit);
</script>

<template>
  <ul>
    <li v-for="(cocktailName, cocktailId) in cocktails" :key="'cocktails' + cocktailId">
      IDが{{ cocktailId }}のカクテルは{{ cocktailName }}
    </li>
  </ul>
  <ul>
    <li
      v-for="(cocktailName, cocktailId, index) in cocktails"
      :key="'cocktailsWithIndex' + cocktailId"
    >
      {{ index + 1 }}: IDが{{ cocktailId }}のカクテルは{{ cocktailName }}
    </li>
  </ul>
</template>
