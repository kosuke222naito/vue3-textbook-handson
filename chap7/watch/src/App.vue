<script setup lang="ts">
import { ref, watch } from "vue";
import type { Cocktail } from "../../interfaces";

const currentCocktailId = ref(1);
const priceMessage = ref("");

const getCocktailInfo = (cocktailId: number): string => {
  const cocktailsInit = new Map<Number, Cocktail>();
  cocktailsInit.set(1, { id: 1, name: "ホワイトレディ", price: 1200 });
  cocktailsInit.set(2, { id: 2, name: "ブルーハワイ", price: 1500 });
  cocktailsInit.set(3, { id: 3, name: "ニューヨーク", price: 1100 });
  cocktailsInit.set(4, { id: 4, name: "マティーニ", price: 1500 });

  const currentCocktail = cocktailsInit.get(cocktailId);
  if (!currentCocktail) {
    return "該当カクテルはありません。";
  }
  return `該当するカクテルは${currentCocktail.name}で、値段は${currentCocktail.price}円です。`;
};

watch(currentCocktailId, (): void => {
  priceMessage.value = getCocktailInfo(currentCocktailId.value);
});

setInterval((): void => {
  currentCocktailId.value = Math.round(Math.random() * 3) + 1;
}, 1000);
</script>

<template>
  <p>現在のカクテル番号: {{ currentCocktailId }}</p>
  <p>{{ priceMessage }}</p>
</template>
