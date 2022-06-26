<template>
  <div class="main">
    <Navbar />

    <div :class="['main__content', !!padding ? 'main__content-padding' : '']">
      <slot />
    </div>

    <Footer />
  </div>
</template>

<script setup lang="ts">
defineProps<{
  padding?: string;
}>();
</script>

<style lang="scss">
.main {
  padding: 4rem;

  &__content-padding {
    padding: 4rem;
  }
}
</style>
