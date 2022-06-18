<template>
  <MainTemplate>
    <div class="index">
      <div class="index__content">
        <slot />
      </div>
      <div class="index__image">
        <img alt="CrabWM logo" src="/images/crab_wm_small.svg" />
      </div>
    </div>
  </MainTemplate>
</template>

<style lang="scss">
@import "styles/mixins";

.index {
  &__image {
    z-index: -1;
    position: absolute;
    right: -4rem;
    bottom: -12rem;
    transform: rotateZ(-10deg);

    img {
      width: 100%;
      height: 100%;
    }
  }
}

@include mq("large") {
  .index {
    &__image {
      opacity: 0.2;
    }
  }
}
</style>
