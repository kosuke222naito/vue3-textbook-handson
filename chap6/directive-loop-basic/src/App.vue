<script setup lang="ts">
import { ref } from "vue";

const cocktailNameListInit: string[] = ["ホワイトレディ", "ブルーハワイ", "ニューヨーク"];
const cocktailNameList = ref(cocktailNameListInit);
</script>

<template>
  <ul>
    <li v-for="cocktailName in cocktailNameList" :key="cocktailName">
      {{ cocktailName }}
    </li>
  </ul>
  <ul>
    <li v-for="(cocktailName, index) in cocktailNameList" :key="cocktailName + index">
      {{ cocktailName }} (インデックス: {{ index }})
    </li>
  </ul>
</template>
