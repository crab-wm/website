<template>
  <main>
    <ContentDoc>
      <template v-slot:not-found>
        <NotFound />
      </template>
    </ContentDoc>
  </main>
</template>

<script setup lang="ts">
definePageMeta({
  layout: "main",
});
</script>
