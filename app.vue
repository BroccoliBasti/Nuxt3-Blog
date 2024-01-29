<template>
  <NuxtLayout>
    <NuxtPage />
  </NuxtLayout>
</template>

<style>
.page-enter-active,
.page-leave-active {
  transition: all 100ms;
}

.page-enter-from,
.page-leave-to {
  opacity: 0;
  filter: blur(10rem), grayscale(1);
  /* scale: 1%; */
}

h2>a,
h3>a {
  text-decoration: none !important;
}

/* @layer base {
  html {
    font-family: "Proxima Nova", system-ui, sans-serif;
  }
} */
</style>