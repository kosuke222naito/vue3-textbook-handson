<script setup lang="ts">
import { ref } from "vue";
import type { Cocktail } from "../../interfaces";
const whiteLadyInit: Cocktail = {
  id: 2345,
  name: "ホワイトレディ",
  price: 1200,
  recipe: "ジン、コアントロー、レモン汁",
};
const whiteLady = ref(whiteLadyInit);

const changeWhiteLadyPrice = () => {
  whiteLady.value.price = 1500;
};
</script>

<template>
  <dl>
    <template v-for="(value, key) in whiteLady" :key>
      <dt>{{ key }}</dt>
      <dt>{{ value }}</dt>
    </template>
  </dl>
  <p>
    値段を1500円に<button
      type="button"
      @click="changeWhiteLadyPrice"
      :disabled="whiteLady.price === 1500"
    >
      変更
    </button>
  </p>
</template>
