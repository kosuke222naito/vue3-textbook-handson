<script setup lang="ts">
import { ref } from "vue";

const cocktailNamesInit = new Map<number, string>();
cocktailNamesInit.set(2345, "ホワイトレディ");
cocktailNamesInit.set(4412, "ブルーハワイ");
cocktailNamesInit.set(6792, "ニューヨーク");
const cocktailNames = ref(new Map(cocktailNamesInit));

const replaceCocktailNames = () => {
  if (
    JSON.stringify([...cocktailNames.value.keys()]) ===
    JSON.stringify([...cocktailNamesInit.keys()])
  ) {
    cocktailNames.value.clear();
    cocktailNames.value.set(3426, "バラライカ");
    cocktailNames.value.set(5517, "XYZ");
    cocktailNames.value.set(7415, "マンハッタン");
  } else {
    cocktailNames.value.clear();
    cocktailNames.value.set(2345, "ホワイトレディ");
    cocktailNames.value.set(4412, "ブルーハワイ");
    cocktailNames.value.set(6792, "ニューヨーク");
  }
};

const addCocktailNames = () => {
  if (cocktailNames.value.has(8894)) {
    return;
  }
  cocktailNames.value.set(8894, "ブルームーン");
};

const deleteFromCocktailNames = () => {
  if (!cocktailNames.value.has(5517)) {
    return;
  }
  cocktailNames.value.delete(5517);
};
</script>

<template>
  <ul>
    <li v-for="[id, cocktailName] in cocktailNames" :key="id">
      IDが{{ id }}のカクテルは{{ cocktailName }}
    </li>
  </ul>
  <p>カクテルの一覧を<button type="button" @click="replaceCocktailNames">切り替える</button></p>
  <p>ブルームーンを一覧に<button type="button" @click="addCocktailNames">追加</button></p>
  <p>
    カクテル一覧からIDが5517のカクテルを
    <button type="button" @click="deleteFromCocktailNames">削除</button>
  </p>
</template>
