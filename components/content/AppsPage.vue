<template>
  <MainTemplate>
    <div class="apps-page">
      <slot />
    </div>
  </MainTemplate>
</template>

<style lang="scss">
.apps-page {
  padding: 4rem;

  &__apps {
    display: grid;
  }
}
</style>
