<script setup lang="ts">
import ArticlePreview from '@/components/ArticlePreview.vue';
</script>

<template>
  <main>
    <ArticlePreview />
  </main>
</template>

<style scoped lang="scss">
main {
  min-height: 100vh; /* fallback */
  min-height: 100dvh;
  padding-inline: 1.5rem;
  display: grid;
  align-content: center;
}
</style>
