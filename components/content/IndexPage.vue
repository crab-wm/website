<template>
  <MainTemplate>
    <div class="index">
      <div class="index__content">
        <div class="index__content__container">
          <slot name="hero" />
        </div>
        <div class="index__content__image">
          <img alt="CrabWM logo" src="/images/crab_wm_small.svg" />
        </div>
      </div>
      <ContentContainer>
        <slot />
      </ContentContainer>
    </div>
  </MainTemplate>
</template>

<style lang="scss">
@import "styles/variables";
@import "styles/mixins";

.index {
  padding: 4rem;

  &__content {
    &__image {
      z-index: -1;
      position: absolute;
      right: -4rem;
      bottom: -6rem;

      img {
        transform: rotateZ(-10deg);
        width: 100%;
        height: 100%;
      }
    }
  }
}

@include mq("large") {
  .index {
    &__content {
      &__image {
        opacity: 0.2;
        width: 50%;
        right: 0;
        bottom: 5rem;
      }
    }
  }
}

@include mq("big") {
  .index {
    &__content {
      &__image {
        opacity: 0.2;
        width: 50%;
        right: 0;
        bottom: 15rem;
      }
    }
  }
}
</style>
<script>
import ContentContainer from "./ContentContainer";
export default {
  components: { ContentContainer },
};
</script>
