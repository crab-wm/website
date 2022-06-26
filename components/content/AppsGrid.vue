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
