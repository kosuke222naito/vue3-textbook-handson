<script setup lang="ts">
import { computed, ref } from "vue";

interface Props {
  id: number;
  name: string;
  email: string;
  points: number;
  note?: string;
}
const props = defineProps<Props>();

const localPoints = ref(props.points);
const localNote = computed((): string => {
  if (!props.note) {
    return "--";
  }
  return props.note;
});

const pointUp = (): void => {
  localPoints.value++;
};
</script>

<template>
  <section class="box">
    <h4>{{ name }}さんの情報</h4>
    <dl>
      <dt>ID</dt>
      <dd>{{ id }}</dd>
      <dt>メールアドレス</dt>
      <dd>{{ email }}</dd>
      <dt>ポイント</dt>
      <dd>{{ localPoints }}</dd>
      <dt>備考</dt>
      <dd>{{ localNote }}</dd>
    </dl>
  </section>
</template>

<style scoped>
.box {
  border: green 1px solid;
  margin: 10px;
}
</style>
