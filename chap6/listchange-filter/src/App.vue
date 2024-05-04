<script setup lang="ts">
import { computed, ref } from "vue";
import { Cocktail } from "../../interfaces.ts";
const cocktailsInit: Cocktail[] = [
  { id: 2345, name: "ホワイトレディ", price: 1200 },
  { id: 4412, name: "ブルーハワイ", price: 1500 },
  { id: 6792, name: "ニューヨーク", price: 1100 },
  { id: 8429, name: "マティーニ", price: 1500 },
];
const cocktails = ref(cocktailsInit);
const cocktails1500Yen = computed((): Cocktail[] => {
  return cocktails.value.filter((cocktail) => cocktail.price === 1500);
});
</script>

<template>
  <section>
    全てのカクテル
    <ul>
      <li v-for="cocktail in cocktails" :key="cocktail.id">
        {{ cocktail.name }}の値段は{{ cocktail.price }}円
      </li>
    </ul>
  </section>
  <section>
    値段が1500円のカクテル
    <ul>
      <li v-for="cocktail in cocktails1500Yen" :key="'cocktail1500yen' + cocktail.id">
        {{ cocktail.name }}の値段は{{ cocktail.price }}円
      </li>
    </ul>
  </section>
</template>
