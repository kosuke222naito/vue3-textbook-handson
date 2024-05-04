<script setup lang="ts">
import { ref } from "vue";

const pBgColor = ref("white");
const pBgColor2 = ref("white");
const onClick = (bgColor?: string): void => {
  if (bgColor) {
    pBgColor.value = bgColor;
  } else {
    pBgColor2.value = getRandomColorCode();
  }
};

const getRandomColorCode = (): string => {
  const hexDigits = "0123456789ABCDEF";
  let color = "#";
  for (let i = 0; i < 6; i++) {
    color += hexDigits[Math.floor(Math.random() * 16)];
  }
  return color;
};
</script>

<template>
  <p @click="onClick('red')" :style="{ backgroundColor: pBgColor }">
    ここをクリックすると赤色に変わります。
  </p>
  <p @click="onClick()" :style="{ backgroundColor: pBgColor2 }">
    ここをクリックするとランダムな色に変わります。
  </p>
</template>
