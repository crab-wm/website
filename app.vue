<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
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

h1 {
  font-size: 3rem;
}

h2 {
  font-size: 2.5rem;
}

h3 {
  font-size: 2.2rem;
}

h4 {
  font-size: 1.8rem;
}

h5 {
  font-size: 1.5rem;
}

h6 {
  font-size: 1rem;
}
</style>
