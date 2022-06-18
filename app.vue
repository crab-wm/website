<template>
  <div>
    <NuxtPage />
  </div>
</template>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@400;700&family=Roboto+Mono:wght@400;700&display=swap");
@import "styles/variables";

* {
  font-family: "Roboto Mono", monospace;
  color: white;
}

a {
  text-decoration: none;
  color: inherit;
}

p > a {
  color: $green;
}

body {
  overflow-x: hidden;
  background: $bg-color;
  padding: 0;
  margin: 0;
}
</style>
