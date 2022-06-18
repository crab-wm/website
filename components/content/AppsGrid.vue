<template>
  <div class="apps-grid">
    <slot />
  </div>
</template>

<style lang="scss">
@import "styles/mixins";

.apps-grid {
  margin-right: 10rem;
  margin-top: 4rem;
  display: grid;
  grid-template-columns: repeat(2, 50%);
  grid-column-gap: 6rem;
  grid-row-gap: 2rem;
}

@include mq("large") {
  .apps-grid {
    grid-template-columns: calc(100% - 4rem);
    margin-right: 0;
  }
}
</style>
