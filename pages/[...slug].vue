<template>
  <main>
    <ContentDoc>
      <template v-slot:not-found>
        <NotFoundOrEmpty />
      </template>
      <template v-slot:empty>
        <NotFoundOrEmpty />
      </template>
    </ContentDoc>
  </main>
</template>

<script setup lang="ts">
definePageMeta({
  layout: "main",
});
</script>
