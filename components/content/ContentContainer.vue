<template>
  <div class="content-container">
    <slot />
  </div>
</template>

<style lang="scss">
@import "styles/variables";

.content-container {
  margin-top: 6rem;
  background: $bg-color;
  padding: 2rem 2rem 2rem 0;
  width: 100%;

  * {
    margin: 0;
  }

  p,
  ul,
  table {
    margin-top: 1rem;
  }

  li {
    margin-top: 0.5rem;
  }

  h1,
  h2,
  h3,
  h4,
  h5,
  h6 {
    margin-top: 2rem;
  }
}
</style>
