<script setup lang="ts">
import { ref, computed } from "vue";

const message = ref("Hello World!");
const messageColor = ref("red");
const messageColor2 = ref("white");
const messageBgColor = ref("black");

const messageStyle = ref({
  color: "white",
  backgroundColor: "black",
});

const messageStyle2 = ref({
  fontSize: "1.5rem",
});

const messageStyle3 = ref({
  color: "pink",
  fontSize: "1.5rem",
});

const textSize = computed((): string => `${Math.round(Math.random() * 25) + 10}pt`);
</script>

<template>
  <p :style="{ color: messageColor }">{{ message }}</p>
  <p :style="{ color: 'pink' }">{{ message }}</p>
  <p :style="{ fontSize: textSize }">{{ message }}</p>
  <p :style="{ color: messageColor2, backgroundColor: messageBgColor }">{{ message }}</p>
  <p :style="{ color: messageColor2, 'background-color': messageBgColor }">{{ message }}</p>
  <p :style="messageStyle">{{ message }}</p>
  <p :style="[messageStyle, messageStyle2]">{{ message }}</p>
  <p :style="[messageStyle, messageStyle3]">{{ message }}</p>
  <p :style="[messageStyle3, messageStyle]">{{ message }}</p>
</template>
