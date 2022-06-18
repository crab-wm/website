<template>
  <div>
    <div class="navbar">
      <div class="navbar__logo">
        <img
          alt="CrabWM logo"
          class="navbar__logo__big"
          src="/images/crab_wm_big_2.svg"
        />
        <img
          alt="CrabWM logo"
          class="navbar__logo__small"
          src="/images/crab_wm_small.svg"
        />
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
        <div
          class="navbar__actions__action navbar__actions__action-mobile"
          @click="onHamburgerClick"
        >
          <img alt="Mobile menu" src="/icons/hamburger.svg" />
        </div>
      </div>
    </div>
    <div class="mobile-links" v-if="mobileLinksVisible">
      <ContentNavigation v-slot="{ navigation }">
        <NuxtLink
          class="mobile-links__link"
          v-for="link in navigation"
          :key="link._path"
          :to="link._path"
        >
          {{ link.label }}
        </NuxtLink>
      </ContentNavigation>
    </div>
  </div>
</template>

<script setup lang="ts">
const mobileLinksVisible = ref(false);

const onHamburgerClick = () =>
  (mobileLinksVisible.value = !mobileLinksVisible.value);
</script>

<style lang="scss">
@import "styles/variables";
@import "styles/mixins";

.navbar {
  display: flex;
  align-items: center;
  justify-content: space-between;

  &__logo {
    height: 2.5rem;

    &__big {
      display: block;
    }

    &__small {
      display: none;
    }

    img {
      height: 100%;
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
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 1.3rem;
      font-weight: bold;

      img {
        filter: invert(1);
        width: 1.5rem;
      }
    }

    &__action-mobile {
      display: none;
    }
  }
}

.mobile-links {
  margin-top: 2rem;
  font-size: 1.3rem;
  display: flex;
  flex-direction: column;
  gap: 1rem;

  .router-link-exact-active {
    color: $green;
    font-weight: bold;
  }
}

@include mq("large") {
  .navbar {
    &__links {
      margin-left: 4rem !important;
    }

    &__logo {
      &__big {
        display: none;
      }

      &__small {
        display: block;
      }
    }
  }
}

@include mq("big") {
  .navbar {
    &__logo {
      &__big {
        display: block;
      }

      &__small {
        display: none;
      }
    }

    &__links {
      display: none;
    }

    &__actions {
      &__action {
        span {
          display: none;
        }
      }

      &__action-mobile {
        display: block;
      }
    }
  }
}

@include mq("small") {
  .navbar {
    &__logo {
      &__big {
        display: none;
      }

      &__small {
        display: block;
      }
    }
  }
}
</style>
