<template>
  <div class="main-template">
    <Navbar />

    <div
      :class="[
        'main-template__content',
        !!padding ? 'main-template__content-padding' : '',
      ]"
    >
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
.main-template {
  &__content-padding {
    padding: 4rem;
  }
}
</style>
