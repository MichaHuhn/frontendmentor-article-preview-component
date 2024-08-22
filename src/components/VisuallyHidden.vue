<script setup lang="ts">
import { ref, onUnmounted } from 'vue';

const forceShow = ref(false);

if (!import.meta.env.PROD) {
  (() => {
    const TOGGLE_KEY = 'AltGraph';
    
    function handleKeyDown(event: KeyboardEvent) {
      if (event.key === TOGGLE_KEY) {
        forceShow.value = true;
      }
    }
    
    function handleKeyUp(event: KeyboardEvent) {
      if (event.key === TOGGLE_KEY) {
        forceShow.value = false;
      }
    }
    
    document.addEventListener('keydown', handleKeyDown);
    document.addEventListener('keyup', handleKeyUp)
    
    onUnmounted(() => {
      document.removeEventListener('keydown', handleKeyDown);
      document.removeEventListener('keyup', handleKeyUp);
    });
  })();
}
</script>

<template>
  <span :class="{ 'visually-hidden': !forceShow }">
    <slot />
  </span>
</template>

<style scoped lang="scss">
.visually-hidden:not(:focus):not(:active) {
  width: 1px;
  height: 1px;
  clip: rect(0 0 0 0);
  clip-path: inset(50%);
  white-space: nowrap;
  overflow: hidden;
  position: absolute;
}
</style>
