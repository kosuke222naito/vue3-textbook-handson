<script setup lang="ts">
import { ref } from "vue";

const cocktailNamesInit = ["ホワイトレディ", "ブルーハワイ", "ニューヨーク"];
const cocktailNames = ref(cocktailNamesInit);

const replaceCocktailNames = () => {
  if (JSON.stringify(cocktailNames.value) === JSON.stringify(cocktailNamesInit)) {
    cocktailNames.value = ["バラライカ", "XYZ", "マンハッタン"];
  } else {
    cocktailNames.value = cocktailNamesInit;
  }
};

const addCocktailNames = () => {
  if (cocktailNames.value.includes("ブルームーン")) {
    return;
  }
  cocktailNames.value.push("ブルームーン");
};

const popCocktailNames = () => {
  if (cocktailNames.value.length === 0) {
    return;
  }
  cocktailNames.value.pop();
};
</script>

<template>
  <ul>
    <li v-for="(cocktailName, index) in cocktailNames" :key="cocktailName">
      {{ cocktailName }}(インデックス: {{ index }})
    </li>
  </ul>
  <p>カクテルの一覧を<button type="button" @click="replaceCocktailNames">切り替える</button></p>
  <p>ブルームーンを一覧に<button type="button" @click="addCocktailNames">追加</button></p>
  <p>
    カクテル一覧から末尾のカクテルを<button type="button" @click="popCocktailNames">削除</button>
  </p>
</template>
