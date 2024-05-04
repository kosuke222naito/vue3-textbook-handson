<script setup lang="ts">
import { computed, ref } from "vue";
import type { Cocktail } from "../../interfaces";

const cocktailsInit = new Map<number, Cocktail>();
cocktailsInit.set(2345, { id: 2345, name: "ホワイトレディ", price: 1200 });
cocktailsInit.set(4412, { id: 4412, name: "ブルーハワイ", price: 1500 });
cocktailsInit.set(6792, { id: 6792, name: "ニューヨーク", price: 1100 });
cocktailsInit.set(8429, { id: 8429, name: "マティーニ", price: 1500 });
const cocktails = ref(cocktailsInit);

const cocktails1500Yen = computed((): Map<number, Cocktail> => {
  const cocktails1500Yen_ = new Map<number, Cocktail>();
  for (const [key, cocktail] of cocktails.value) {
    if (cocktail.price === 1500) {
      cocktails1500Yen_.set(key, cocktail);
    }
  }
  return cocktails1500Yen_;
});

const changeWhiteLadyPrice = () => {
  (cocktails.value.get(2345) as Cocktail).price = 1500;
};
</script>

<template>
  <section>
    全てのカクテル
    <ul>
      <li v-for="[key, cocktail] in cocktails" :key>
        {{ cocktail.name }}の値段は{{ cocktail.price }}円
      </li>
    </ul>
  </section>
  <section>
    値段が1500円のカクテル
    <ul>
      <li v-for="[key, cocktail] in cocktails1500Yen" :key="'cocktail1500Yen' + key">
        {{ cocktail.name }}の値段は{{ cocktail.price }}円
      </li>
    </ul>
  </section>
  <p>
    ホワイトレディの値段を1500円に<button
      type="button"
      @click="changeWhiteLadyPrice"
      :disabled="cocktails.get(2345)?.price === 1500"
    >
      変更
    </button>
  </p>
</template>
