<script setup lang="ts">
import { ref } from "vue";
import OneInfo from "./components/OneInfo.vue";

const propsTitle = ref("発生した乱数");
const randomNumberInit = Math.round(Math.random() * 100);
const randomNumber = ref(randomNumberInit);
</script>

<template>
  <h1>Props基礎</h1>
  <section>
    <h2>テンプレート変数を利用</h2>
    <OneInfo :title="propsTitle" :content="randomNumber" />
  </section>
</template>
