<script setup lang="ts">
import { ref, computed } from "vue";

const message = ref("Hello World!");
const isMessageColorRed = ref(true);
const isBgColorBlack = ref(false);

const messageStyle = ref({
  isMessageColorRed: false,
  isBgColorBlack: true,
});

const computedStyle = computed(
  (): {
    textColorRed: boolean;
    bgColorBlack: boolean;
  } => {
    return {
      textColorRed: !!Math.round(Math.random()),
      bgColorBlack: !!Math.round(Math.random()),
    };
  },
);
</script>

<template>
  <p :class="{ textColorRed: true, isBgColorBlack: true }">{{ message }}</p>
  <p :class="{ textColorRed: isMessageColorRed, isBgColorBlack: isBgColorBlack }">{{ message }}</p>
  <p :class="{ textColorPink: true }">{{ message }}</p>
  <p :class="{ 'text-color-pink': true }">{{ message }}</p>
  <p
    class="textColorPink"
    :class="{ textColorRed: isMessageColorRed, bgColorBlack: isBgColorBlack }"
  >
    {{ message }}
  </p>
  <p class="textSize24px" :class="messageStyle">{{ message }}</p>
  <p :class="computedStyle">{{ message }}</p>
</template>

<style>
.textColorRed {
  color: red;
}

.text-color-pink {
  color: pink;
}

.bgColorBlack {
  background-color: black;
}

.textSize24px {
  font-size: 24px;
}
</style>
