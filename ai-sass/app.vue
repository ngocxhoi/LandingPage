<template>
  <div class="bg-brand-dark pb-28">
    <NuxtRouteAnnouncer />
    <Navigator />
    <NuxtPage class="w-full" />
    <Footer />
  </div>
</template>

<script setup lang="ts">
const appConfig = useAppConfig();

useHead({
  titleTemplate(title): any {
    return title ? `${title} / ${appConfig.title}` : appConfig.title;
  },
});
</script>

<style>
:root {
  --foreground-rgb: 0, 0, 0;
  --background-start-rgb: 214, 219, 220;
  --background-end-rgb: 255, 255, 255;
}

@media (prefers-color-scheme: dark) {
  :root {
    --foreground-rgb: 255, 255, 255;
    --background-start-rgb: 0, 0, 0;
    --background-end-rgb: 0, 0, 0;
  }
}

body {
  color: rgb(var(--foreground-rgb));
  background: linear-gradient(
      to bottom,
      transparent,
      rgb(var(--background-end-rgb))
    )
    rgb(var(--background-start-rgb));
}

/* @layer utilities {
  .text-balance {
    text-wrap: balance;
  }
} */

.animate-slide {
  animation: 15s slide linear infinite;
}

@keyframes slide {
  from {
    transform: translateX(0);
  }
  to {
    transform: translateX(-100%);
  }
}
</style>
