<script setup lang="ts">
import { ref } from "vue";

const cocktailsInit: Cocktail[] = [
  { id: 2345, name: "ホワイトレディ", price: 1200 },
  { id: 4412, name: "ブルーハワイ", price: 1500 },
  { id: 6792, name: "ニューヨーク", price: 1100 },
  { id: 8429, name: "マティーニ", price: 1500 },
];
const cocktails = ref(cocktailsInit);

interface Cocktail {
  id: number;
  name: string;
  price: number;
}
</script>

<template>
  <ul>
    <li v-for="cocktail in cocktails" :key="cocktail.id">
      {{ cocktail.name }}の値段は{{ cocktail.price }}f円
    </li>
  </ul>
</template>
