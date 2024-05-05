<script setup lang="ts">
import { ref } from "vue";
import OneInfo from "./components/OneInfo.vue";

const weathersInit = new Map<number, Weather>();
weathersInit.set(1, { id: 1, title: "今日の天気", content: "晴れ" });
weathersInit.set(2, { id: 2, title: "明日の天気", content: "雨" });
weathersInit.set(3, { id: 3, title: "明後日の天気", content: "雪" });
const weathers = ref(weathersInit);

interface Weather {
  id: number;
  title: string;
  content: string;
}
</script>

<template>
  <h1>Props基礎</h1>
  <section>
    <h2>ループでコンポーネントを生成</h2>
    <OneInfo
      v-for="[key, weather] in weathers"
      :key
      :title="weather.title"
      :content="weather.content"
    />
  </section>
</template>
