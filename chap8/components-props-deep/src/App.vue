<script setup lang="ts">
import { computed, ref } from "vue";
import OneMember from "./components/OneMember.vue";

const membersInit = new Map<number, Member>();
membersInit.set(33456, {
  id: 33456,
  name: "田中太郎",
  email: "bow@example.com",
  points: 35,
  note: "初回入会特典あり",
});
membersInit.set(47783, {
  id: 47783,
  name: "鈴木二郎",
  email: "mue@example.com",
  points: 100,
});
const members = ref(membersInit);

const totalPoints = computed((): number => {
  return [...members.value.values()].reduce((total, member) => total + member.points, 0);
});

interface Member {
  id: number;
  name: string;
  email: string;
  points: number;
  note?: string;
}
</script>

<template>
  <section>
    <h1>会員リスト</h1>
    <p>全会員の合計ポイント: {{ totalPoints }}</p>
    <OneMember
      v-for="[id, member] in members"
      :key="id"
      :id
      :name="member.name"
      :email="member.email"
      :points="member.points"
      :note="member.note"
    />
  </section>
</template>
