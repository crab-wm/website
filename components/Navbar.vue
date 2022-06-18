<template>
  <div class="navbar">
    <div class="navbar__logo">
      <img alt="CrabWM logo" src="/images/crab_wm_big_2.svg" />
    </div>
    <div class="navbar__links">
      <ContentNavigation v-slot="{ navigation }">
        <NuxtLink
          class="navbar__links__link"
          v-for="link in navigation"
          :key="link._path"
          :to="link._path"
        >
          {{ link.label }}
        </NuxtLink>
      </ContentNavigation>
    </div>
    <div class="navbar__actions">
      <NuxtLink to="https://github.com/crab-wm">
        <div class="navbar__actions__action">
          <img alt="GitHub logo" src="/icons/github.svg" />
          <span>GitHub</span>
        </div>
      </NuxtLink>
    </div>
  </div>
</template>

<style lang="scss">
@import "styles/variables";

.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;

  &__logo {
    width: 12rem;

    img {
      width: 100%;
    }
  }

  &__links {
    flex-grow: 1;
    margin-left: 10rem;
    gap: 3rem;
    display: flex;
    align-items: center;
    font-size: 1.3rem;

    &__link {
      transition: opacity 0.1s ease-in-out;

      &:hover {
        opacity: 0.8;
      }
    }

    .router-link-exact-active {
      color: $green;
      font-weight: bold;
    }
  }

  &__actions {
    display: flex;
    gap: 3rem;
    align-items: center;
    font-size: 1.3rem;

    &__action {
      display: flex;
      align-items: center;
      gap: 1.3rem;
      font-weight: bold;

      img {
        filter: invert(1);
        width: 1.5rem;
      }
    }
  }
}
</style>
