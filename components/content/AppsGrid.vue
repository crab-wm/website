<template>
  <div class="apps-grid">
    <AppBlock v-for="app in apps" :image="app.image" :url="app._path">
      <template v-slot:name>{{ app.name }}</template>
      {{ app.info }}
    </AppBlock>
  </div>
</template>

<script setup lang="ts">
import ContentApp from "~/types/ContentApp";
import { ParsedContent } from "@nuxt/content/dist/runtime/types";

const apps = (await queryContent("apps").skip(1).find()) as (ParsedContent &
  ContentApp)[];
</script>

<style lang="scss">
@import "styles/mixins";

.apps-grid {
  margin-top: 4rem;
  display: grid;
  grid-template-columns: repeat(2, 50%);
  grid-row-gap: 2rem;
  grid-column-gap: 2rem;
  width: calc(100% - 2rem);
}

@include mq("large") {
  .apps-grid {
    grid-template-columns: 100%;
    margin-right: 0;
    width: 100%;
  }
}
</style>
