<script setup lang="ts">
import { ref } from 'vue'

const url = ref('https://vuejs.org/')
</script>

<template>
  <p><a :href="url" target="_blank">Vueのサイト</a></p>
  <p><a :href="url + 'guide/introduction.html'" target="_blank">Vueのガイドページ</a></p>
</template>
