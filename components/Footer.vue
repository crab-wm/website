<template>
  <div class="footer">
    <div class="footer__title">
      <h1>CrabWM</h1>
      <p>CrabWM is going to be good. <u>REALLY</u> good.</p>
    </div>
    <div class="footer__image">
      <img alt="CrabWM logo" src="/images/crab_wm_small.svg" />
    </div>
  </div>
</template>

<style lang="scss">
@import "styles/variables";

.footer {
  margin-top: 5rem;
  background: $bg-secondary-color;
  padding: 4rem;
  display: flex;
  align-items: center;
  justify-content: space-between;

  &__image {
    width: 4rem;

    img {
      width: 100%;
    }
  }
}
</style>
