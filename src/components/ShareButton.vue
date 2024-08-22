<script setup lang="ts">
import VisuallyHidden from '@/components/VisuallyHidden.vue';
</script>

<template>
  <button>
    <svg xmlns="http://www.w3.org/2000/svg" width="15" height="13"><path fill="currentColor" d="M15 6.495L8.766.014V3.88H7.441C3.33 3.88 0 7.039 0 10.936v2.049l.589-.612C2.59 10.294 5.422 9.11 8.39 9.11h.375v3.867L15 6.495z"/></svg>
    <VisuallyHidden>share</VisuallyHidden>
  </button>
</template>

<style scoped lang="scss">
button {
  --size: 2rem;
  
  width: var(--size);
  height: var(--size);
  margin-left: auto;
  padding: 0;
  color: var(--color-desaturated-dark-blue);
  background-color: var(--color-light-grayish-blue);
  border: none;
  border-radius: 100vmax;
  cursor: pointer;
  display: grid;
  place-content: center;
  
  &:hover, &:focus-visible {
    color: white;
    background-color: var(--color-desaturated-dark-blue);
  }
}
</style>
