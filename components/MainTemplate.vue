<template>
  <div class="main-template">
    <Navbar />

    <div class="main-template__content">
      <slot />
    </div>
  </div>
</template>

<style lang="scss">
.main-template {
  padding: 4rem;

  &__content {
    margin-top: 7rem;
  }
}
</style>
