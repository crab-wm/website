<template>
  <div class="hero-section">
    <div class="hero-section__left">
      <div class="hero-section__left__titles">
        <h3>{{ subtitle }}</h3>
        <h1>{{ title }}</h1>
      </div>
      <div class="hero-section__left__actions">
        <NuxtLink :to="mainUrl">
          <button class="hero-section__left__actions__main">
            <img :alt="mainLabel" :src="`/icon/${mainIcon}.svg`" />
            <span>{{ mainLabel }}</span>
          </button>
        </NuxtLink>
        <NuxtLink :to="secondaryUrl">
          <button class="hero-section__left__actions__secondary">
            <img :alt="secondaryLabel" :src="`/icon/${secondaryIcon}.svg`" />
            <span>{{ secondaryLabel }}</span>
          </button>
        </NuxtLink>
      </div>
    </div>
    <div class="hero-section__image" v-if="!!image">
      <img alt="" :src="`/images/${image}`" />
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  mainIcon: string;
  mainLabel: string;
  mainUrl: string;
  secondaryIcon: string;
  secondaryLabel: string;
  secondaryUrl: string;
  subtitle: string;
  title: string;
  image?: string;
}>();
</script>

<style lang="scss">
@import "styles/variables";
@import "styles/mixins";

.hero-section {
  display: flex;
  align-items: center;
  justify-content: space-between;

  &__left {
    &__titles {
      h3 {
        font-family: "Poppins", sans-serif;
        font-size: 3rem;
        font-weight: normal;
      }

      h1 {
        margin-top: -2rem;
        font-family: "Poppins", sans-serif;
        font-size: 5rem;
      }
    }

    &__actions {
      margin-top: 3rem;
      display: flex;
      align-items: center;
      gap: 1rem;

      button {
        cursor: pointer;
        outline: none;
        transition: opacity 0.1s ease-in-out;
        display: flex;
        align-items: center;
        padding: 1rem 3rem;
        gap: 1rem;
        border: 3px $green solid;

        &:hover {
          opacity: 0.8;
        }

        img {
          width: 1.7rem;
        }

        span {
          font-weight: bold;
          font-size: 1.3rem;
        }
      }

      &__main {
        border: none;
        background: $green;

        span {
          color: black;
        }
      }

      &__secondary {
        background: $bg-color;
      }
    }
  }

  &__image {
    width: 15rem;

    img {
      width: 100%;
    }
  }
}

@include mq("large") {
  .hero-section {
    flex-direction: column-reverse;
    align-items: start;
    justify-content: normal;
    gap: 1rem;

    &__image {
      width: 5rem;
    }
  }
}

@include mq("big") {
  .hero-section {
    &__left {
      &__titles {
        h3 {
          font-size: 2rem;
        }

        h1 {
          font-size: 3.5rem;
        }
      }

      &__actions {
        flex-direction: column;
        align-items: start;
      }
    }
  }
}

@include mq("small") {
  .hero-section {
    &__left {
      &__titles {
        h3 {
          font-size: 1.5rem;
        }

        h1 {
          font-size: 2.4rem;
          margin-top: -1rem;
        }
      }

      &__actions {
        button {
          padding: 0.7rem 2rem;

          img {
            height: 1.3rem;
          }

          span {
            font-size: 1rem;
          }
        }
      }
    }
  }
}
</style>
