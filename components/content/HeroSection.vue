<template>
  <div class="hero-section">
    <div class="hero-section__titles">
      <h3>{{ subtitle }}</h3>
      <h1>{{ title }}</h1>
    </div>
    <div class="hero-section__actions">
      <a :href="mainUrl">
        <button class="hero-section__actions__main">
          <img :alt="mainLabel" :src="`/icons/${mainIcon}.svg`" />
          <span>{{ mainLabel }}</span>
        </button>
      </a>
      <a :href="secondaryUrl">
        <button class="hero-section__actions__secondary">
          <img :alt="secondaryLabel" :src="`/icons/${secondaryIcon}.svg`" />
          <span>{{ secondaryLabel }}</span>
        </button>
      </a>
    </div>
  </div>
</template>

<script setup lang="ts">
defineProps<{
  mainIcon: string,
  mainLabel: string,
  mainUrl: string,
  secondaryIcon: string,
  secondaryLabel: string,
  secondaryUrl: string,
  subtitle: string,
  title: string
}>();
</script>