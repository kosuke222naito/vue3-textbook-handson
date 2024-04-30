<script setup lang="ts">
import { ref } from "vue";

const message = ref("まだです");
const onEnterKeyPress = (): void => {
  message.value = "エンターが押されました";
};
const onRightButtonClick = (): void => {
  message.value = "右クリックされました";
};
const onClickWithShift = (): void => {
  message.value = "シフトを押しながらクリックされました";
};
</script>

<template>
  <p>{{ message }}</p>
  <input type="text" @keydown.enter="onEnterKeyPress" />
  <br />
  <button @click.right.prevent="onRightButtonClick">右クリック</button>
  <br />
  <button @click.shift="onClickWithShift">シフトクリック</button>
  <br />
</template>
