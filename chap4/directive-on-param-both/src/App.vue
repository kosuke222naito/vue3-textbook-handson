<script setup lang="ts">
import { ref } from "vue";

const message = ref("イベント前(ここをクリック！)");
const bgColorEvent = ref("white");

const onClickWithEvent = (bgColor: string, event: MouseEvent): void => {
  bgColorEvent.value = bgColor;
  message.value = event.timeStamp.toString();
};
</script>

<template>
  <p @click="onClickWithEvent('green', $event)" :style="{ backgroundColor: 'bgColorEvent' }">
    {{ message }}
  </p>
</template>
