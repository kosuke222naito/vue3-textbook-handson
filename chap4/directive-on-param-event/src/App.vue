<script setup lang="ts">
import { ref } from "vue";

const mousePointerInit = { x: 0, y: 0 };
const mousePointer = ref(mousePointerInit);
const onMouseMove = (event: MouseEvent): void => {
  mousePointer.value = { x: event.offsetX, y: event.offsetY };
};
const onMouseLeave = (): void => {
  mousePointer.value = mousePointerInit;
};
</script>
<template>
  <section>
    <img
      src="./assets/logo.svg"
      alt="VueLogo"
      @mousemove="onMouseMove"
      @mouseleave="onMouseLeave"
      class="vueLogo"
    />
    <p>ポインタの位置: x={{ mousePointer.x }}, y={{ mousePointer.y }}</p>
  </section>
</template>

<style>
.vueLogo {
  width: 200px;
}
</style>
