<script setup lang="ts">
import { ref, computed } from "vue";

const radiusInit = Math.round(Math.random() * 10);
const PI = ref(3.14);
const radius = ref(radiusInit);
const area = computed((): number => radius.value * radius.value * PI.value);

setInterval(() => {
  radius.value = Math.round(Math.random() * 10);
}, 1000);
</script>

<template>
  <p>半径{{ radius }}の円の面積を円周率{{ PI }}で計算すると、{{ area }}になる。</p>
</template>
