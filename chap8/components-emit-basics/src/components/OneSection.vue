<script setup lang="ts">
interface Props {
  randomNumber: number;
}

interface Emits {
  (event: "onUpdateRandomNumberButtonClick"): void;
}

defineProps<Props>();
const emit = defineEmits<Emits>();

const onUpdateRandomNumberButtonClick = (): void => {
  emit("onUpdateRandomNumberButtonClick");
};
</script>

<template>
  <section class="box">
    <p>子コンポーネントで乱数を表示: {{ randomNumber }}</p>
    <button type="button" @click="onUpdateRandomNumberButtonClick">新たな乱数</button>
  </section>
</template>

<style scoped>
.box {
  border: green 1px solid;
  margin: 10px;
}
</style>
