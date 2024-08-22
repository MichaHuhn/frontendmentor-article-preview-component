<script setup lang="ts">
import { ref } from 'vue';

const forceShow = ref(false);

if (!import.meta.env.PROD) {
  document.addEventListener('keydown', event => {
    if (event.key === 'AltGraph') {
      forceShow.value = !forceShow.value;
    }
  });
}
</script>

<template>
  <span :class="{ 'visually-hidden': !forceShow }"><slot /></span>
</template>

<style scoped lang="scss">
.visually-hidden {
  width: 1px;
  height: 1px;
  margin: -1px;
  padding: 0;
  border: 0;
  clip: rect(0 0 0 0);
  position: absolute;
  display: inline-block;
  overflow: hidden;
}
</style>
