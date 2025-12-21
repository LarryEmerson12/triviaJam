<script setup lang="ts">
import type { NavigationMenuItem, ButtonProps } from "@nuxt/ui";

const route = useRoute();

const headerItems = computed<NavigationMenuItem[]>(() => [
  {
    label: "Docs",
    to: "/docs/getting-started",
    icon: "i-lucide-book-open",
    active: route.path.startsWith("/docs/getting-started"),
  },
  {
    label: "Templates",
    to: "/templates",
    icon: "i-lucide-box",
    active: route.path.startsWith("/templates"),
  },
  {
    label: "Join a Game",
    to: "/join",
    icon: "i-lucide-rocket",
    active: route.path.startsWith("/join"),
  },
]);

const footerItems: NavigationMenuItem[] = [
  {
    label: "Join a Game",
    to: "https://go.nuxt.com/figma-ui",
    target: "_blank",
  }, {
    label: "Privacy Policy",
    to: "/privacy-policy",
  },
];

const links = ref<ButtonProps[]>([
  {
    label: "Get started",
    to: "/docs/getting-started",
    icon: "i-lucide-square-play",
  },
  {
    label: "Learn more",
    to: "/docs/getting-started/theme/design-system",
    color: "neutral" as const,
    variant: "subtle" as const,
    trailingIcon: "i-lucide-arrow-right",
  },
]);
</script>

<template>
  <UApp>
    <UHeader title="TriviaJam">
      <UNavigationMenu :items="headerItems" variant="link" />
      <template #right>
        <UColorModeSwitch />
        <UTooltip text="Open on GitHub" :kbds="['meta', 'G']">
          <UButton
            color="neutral"
            variant="ghost"
            to="https://github.com/LarryEmerson12/triviaJam"
            target="_blank"
            icon="i-simple-icons-github"
            aria-label="GitHub"
          />
        </UTooltip>
      </template>
    </UHeader>

    <UMain>
      <NuxtLayout>
        <NuxtPage>
          <UPageHero
            title="Create quizzes fast"
            description="Generate quizzes faster than any other application. TriviaJam is a streamlined, free-to-use platform for instantly creating and deploying customizable trivia games."
            headline="New update!"
            :links="links"
          />
        </NuxtPage>
      </NuxtLayout>
    </UMain>

    <UFooter>
      <template #left>
        <p class="text-muted text-sm">
          Copyright © {{ new Date().getFullYear() }}
        </p>
      </template>

      <UNavigationMenu :items="footerItems" variant="link" />

      <template #right>
        <UButton
          icon="i-simple-icons-discord"
          color="neutral"
          variant="ghost"
          to="https://go.nuxt.com/discord"
          target="_blank"
          aria-label="Discord"
        />
        <UButton
          icon="i-simple-icons-x"
          color="neutral"
          variant="ghost"
          to="https://go.nuxt.com/x"
          target="_blank"
          aria-label="X"
        />
        <UButton
          icon="i-simple-icons-github"
          color="neutral"
          variant="ghost"
          to="https://github.com/LarryEmerson12/triviaJam"
          target="_blank"
          aria-label="GitHub"
        />
      </template>
    </UFooter>
  </UApp>
</template>
