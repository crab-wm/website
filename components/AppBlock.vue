<template>
  <NuxtLink class="app-block" :to="url">
    <div class="app-block__image">
      <img alt="" :src="`/images/${image}`" />
    </div>
    <div class="app-block__content">
      <h4><slot name="name" /></h4>
      <p><slot /></p>
    </div>
  </NuxtLink>
</template>

<script setup lang="ts">
defineProps<{
  image: string;
  url: string;
}>();
</script>

<style lang="scss">
@import "styles/variables";
@import "styles/mixins";

.app-block {
  background: $bg-secondary-color;
  padding: 2rem;
  display: flex;
  gap: 2rem;
  align-items: center;

  &__image {
    height: 5rem;

    img {
      height: 100%;
    }
  }

  &__content {
    h4,
    h4 > p {
      margin: 0 !important;
    }

    p {
      margin: 0.8rem 0 0;
    }
  }
}

@include mq("large") {
  .app-block {
    flex-direction: column;
    align-items: start;
    height: auto;
  }
}
</style>
