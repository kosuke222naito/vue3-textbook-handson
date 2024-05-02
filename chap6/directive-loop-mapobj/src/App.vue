<script setup lang="ts">
import { ref } from "vue";
import type { Cocktail } from "../../interfaces";
const cocktailsInit = new Map<number, Cocktail>();
cocktailsInit.set(2345, { id: 2345, name: "ホワイトレディ", price: 1200 });
cocktailsInit.set(4412, { id: 4412, name: "ブルーハワイ", price: 1500 });
cocktailsInit.set(6792, { id: 6792, name: "ニューヨーク", price: 1100 });
cocktailsInit.set(8429, { id: 8429, name: "マティーニ", price: 1500 });
const cocktails = ref(cocktailsInit);
</script>

<template>
  <ul>
    <li v-for="[id, cocktail] in cocktails" :key="id">
      {{ cocktail.name }}の値段は{{ cocktail.price }}円
    </li>
  </ul>
</template>
