<script setup lang="ts">
import { computed, ref } from "vue";

interface Cocktail {
  id: number;
  name: string;
  price: number;
  recipe?: string;
}

const cocktailsInit = new Map<number, Cocktail>();
cocktailsInit.set(1, { id: 1, name: "ホワイトレディ", price: 1200 });
cocktailsInit.set(2, { id: 2, name: "ブルーハワイ", price: 1500 });
cocktailsInit.set(3, { id: 3, name: "ニューヨーク", price: 1100 });
cocktailsInit.set(4, { id: 4, name: "マティーニ", price: 1500 });
const cocktails = ref(new Map(cocktailsInit));

const currentCocktailId = ref(1);
const priceMessage = computed((): string => {
  const currentCocktail = cocktailsInit.get(currentCocktailId.value);
  if (!currentCocktail) {
    return "該当カクテルはありません。";
  }
  return `該当するカクテルは${currentCocktail.name}で、値段は${currentCocktail.price}円です。`;
});

setInterval((): void => {
  currentCocktailId.value = Math.round(Math.random() * 3) + 1;
}, 1000);
</script>

<template>
  <p>現在のカクテル番号: {{ currentCocktailId }}</p>
  <p>{{ priceMessage }}</p>
</template>
