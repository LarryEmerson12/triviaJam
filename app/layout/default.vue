<script setup lang="ts">
import { ref } from "vue";
import type { NavigationMenuItem } from "@nuxt/ui";

const route = useRoute();

const headerItems = ref<NavigationMenuItem[]>([
  { label: "Docs", to: "/docs/getting-started" },
  { label: "Templates", to: "/templates" },
  { label: "Join a Game", to: "/join" },
  { label: "Login", to: "/login" },
]);

const footerItems = ref<NavigationMenuItem[]>([
  { label: "Join a Game", to: "#" },
  { label: "Privacy Policy", to: "#" },
]);
</script>

<template>
  <UApp>
    <UHeader title="TriviaJam">
      <UNavigationMenu :items="headerItems" variant="link" />
    </UHeader>

    <UMain>
      <NuxtPage />
    </UMain>

    <UFooter>
      <UNavigationMenu :items="footerItems" variant="link" />
    </UFooter>
  </UApp>
</template>